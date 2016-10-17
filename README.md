# Cocos2dx-3.x
game engine


Sprite creation
```cpp
auto sprite = Sprite::create("boy1.png");
// position the sprite on the center of the screen
sprite->setPosition(Vec2(visibleSize.width/2 + origin.x, visibleSize.height/2 + origin.y));
// add the sprite as a child to this layer
this->addChild(sprite, 0);
```
Particle system

```cpp
auto emitter = ParticleGalaxy::create();
this->addChild(emitter,10);
```

Custom particles using a .plist file(remember to include texture image in the resources folder)
```cpp

auto m_emitter = ParticleSystemQuad::create("kk.plist");
m_emitter->setPosition(Vec2(visibleSize.width/2 + origin.x+40, visibleSize.height/2 + origin.y));
m_emitter->setVisible(true);
m_emitter->retain();
this->addChild(m_emitter,40);
```
Loading  a level file from TMX file
```cpp
auto tmxMap = TMXTiledMap::create("level1.tmx");
this->addChild(tmxMap,90,99);
```
Spritesheet animation

```cpp
auto cache = SpriteFrameCache::getInstance();
cache->addSpriteFramesWithFile("run.plist");
Vector<SpriteFrame*> frames = Vector<SpriteFrame*>();


frames.pushBack(cache->getSpriteFrameByName("0001.png"));
frames.pushBack(cache->getSpriteFrameByName("0002.png"));
frames.pushBack(cache->getSpriteFrameByName("0003.png"));
frames.pushBack(cache->getSpriteFrameByName("0004.png"));
frames.pushBack(cache->getSpriteFrameByName("0005.png"));
frames.pushBack(cache->getSpriteFrameByName("0006.png"));
Animation* anim = cocos2d::Animation::createWithSpriteFrames(frames, 0.1f, 1);

Animate* anim_action = cocos2d::Animate::create(anim);
auto sprite = Sprite::create("boy1.png");
//sprite is already added to scene elsewhere and ready to go
sprite->runAction(RepeatForever::create(anim_action));
sprite->setPosition(Vec2(visibleSize.width/2 + origin.x, visibleSize.height/2 + origin.y));
this->addChild(sprite, 2);
```

Flip sprites
```cpp
sprite->setFlippedX(true); 
```


Buttons
```cpp

#include "ui/CocosGUI.h"
using namespace ui;

 auto BRight = Button::create("left.png");
 BRight->setPosition(Vec2(visibleSize.width/2 + origin.x-100, visibleSize.height/2 + origin.y));
 this->addChild(BRight, 60);

```
