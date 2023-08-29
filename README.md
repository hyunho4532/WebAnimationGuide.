# WebAnimationGuide.
웹 애니메이션 GSAP 이용하여 애니메이션을 적용시켜보자!!

## Tweens
> 모든 애니메이션이 작동하는 역할.

<br>

### Common methods for creating a Tween
> gsap.to()
```javascript
gsap.to(
    '.elem', {
        duration: 1,
        x: 100,
        y: 100, 
        rotation: 45
    }
);
```

<br>

> gsap.from()
```javascript
gsap.from(
    '.elem', {
        duration: 1,
        x: 100,
        y: 100, 
        rotation: 45
    }
);
```

<br>

> gsap.fromTo()
```javascript
gsap.fromTo(
    '.elem', {
        duration: 1,
        x: -100,
        y: -100, 
        rotation: 45
    }, {
        duration: 1,
        x: 100,
        y: 100, 
        rotation: 45
    }
);
```

<br>

### Staggers
> 각 개체의 애니메이션의 시작 사이에 약간의 지연시간을 넣어 보다 쉽게 제어할 수 있다.
```javascript
gsap.from(".box", {
  duration: 2,
  scale: 0.5, 
  opacity: 0, 
  delay: 0.5, 
  stagger: 0.2,
  ease: "elastic", 
  force3D: true
});

document.querySelectorAll(".box").forEach(function(box) {
  box.addEventListener("click", function() {
    gsap.to(".box", {
      duration: 0.5, 
      opacity: 0, 
      y: -100, 
      stagger: 0.1,
      ease: "back.in"
    });
  });
});
```

<br>

### Timeline

> 타임라인을 사용하면 복잡한 시퀀스의 애니메이션을 아주 간단하게 만들 수 있다.
```javascript
var tl = gsap.timeline();

tl.to(".green", {duration: 1, x: 200});
tl.to(".orange", {duration: 1, x: 200, scale: 0.2});
tl.to(".grey", {duration: 1, x: 200, scale: 2, y: 20});
```
