---
layout: post
categories: Unity
published_at: Thu Mar 30 2023 18:50:20 GMT+0900
---

{% include embed-bookmark.html url = "https://docs.unity3d.com/kr/2021.3/Manual/class-InputManager.html" %}


# Input Manager

유니티에서 입력을 담당하는 매니저다.

새로운 입력 축을 생성하려면 Input Manager를 이용하면 된다.

## 입력의 종류

* **Key** : <span class="green">키보드</span>로부터 받는 입력.
* **Button** : <span class="green">컨트롤러</span>로부터 받는 입력.
* **Virtual Axis** : 가상의 입력 축, 버튼이나 키를 이용해 컨트롤을 하면 이 축은 항상 `[-1, 1]` 범위 내에서 값을 반환한다.

## Virtual Axes

프로젝트를 생성하면 기본으로 몇 개의 입력 축들이 만들어져 있다. wasd나 마우스, 조이스틱 같은 입력들은 대부분의 프로젝트에서 필수적으로 입력을 받아야 하기 때문이다.

항상 `[-1, 1]`사이의 값을 반환하지만 몇몇 키들이나 버튼들은 -1, 0, 1중 하나만을 반환한다.

# 예시

```csharp
Input.GetAxis("Mouse X"); // 마우스의 좌우 움직임
Input.GetKey("space"); // space키를 누르고 있는가?
Input.GetKeyDown("W"); // ??
Input.GetButtonDown("Fire1"); // Fire1로 지정된 키가 눌렸는가?
```

주의할 점은 `Input.GetKeyDown`과 `Input.GetKey`가 비슷해보인다는 거다.

공식 문서를 읽어보면 `Input.GetKey`은 유저가 키를 누르고 있는 동안 `true`를 반환한다.

반면 `Input.GetKeyDown`은 **<span class="orange">유저가 처음 키를 누르는 프레임</span>**에만 `true`이고, **<span class="orange">키를 뗐다가 다시 누르기 전까지</span>**는 `false`를 반환한다.

`Input.GetButton`과 `Input.GetButtonDown`도 똑같이 생각할 수 있다.

