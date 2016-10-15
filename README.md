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

