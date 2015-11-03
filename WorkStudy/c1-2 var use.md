### 开发中变量重复使用

#### 问题描述
- 平台:cocosx
- 语言:c++
- 在开发Bhug1056拼图功能时，定义了公共变量tool,
- 每次在TouchEnd是，tool变量执行动画0.5秒后，再获取tool的Texture,创建另一个Sprite来显示。
- 这样出现，快速Touch,在上1个tool还没有释放，下1个tool已经改变，创建的Sprite不对。

#### 解决思路
- 从1个不变的容器中，如iconVec中，根据Tag或UserData,获取Texture,创建Sprite
- 要改变的Tool变量，不做任何动画等操作，只用来显示，显示完后，马上释放
```
auto icon1 = iconTempVec.at(newIndex);	//iconTempVec 只是容器，第一次填充数据后，不会改变
auto tu1 = Sprite::createWithTexture(icon1->getTexture());
this->addChild(tu1,200);
tu1->setPosition(Vec2(100,100));

//位移动画
tu1->runAction(Sequence::create(MoveTo::create(0.3, pp1),CallFunc::create([=]{
    tu1->setLocalZOrder(200);
}),nullptr));

```

#### 较好的方法，能解决同步问题
- 所有的变量，创建后，在使用过程中，都不会改变，
- 数组tool,使用Map存放
```
void Spa::onToolTouchMoved(Ref* pSender){
    auto icon = (ButtonSprite2*)pSender;
    int iid = icon->getTag();
    auto selIcon = getSelIcon(iid);
    selIcon->setPosition(point1);
}

//通过Map来存放工具，解决快速拖动，并发引起的问题
Sprite* Spa::getSelIcon(int iid)
{
    string name = getName(iid);
    if (mapIcon.find(name) != mapIcon.end()){
        auto icon = mapIcon.find(name)->second;
        return icon;
    }else{
        auto toolData = getToolData(iid);
        
        string iconName = StringUtils::format("spaui/%s_u.png",toolData->getName().c_str());
        
        auto selIcon = Sprite::create(iconName);
        selIcon->setAnchorPoint(Vec2(toolData->getAx(),toolData->getAy()));
        this->addChild(selIcon,500);
        mapIcon.insert(name, selIcon);
        return selIcon;
    }
}    

```

#### 使用对象的方法，每个工具1个对象，弊端，工具对象可能太多

