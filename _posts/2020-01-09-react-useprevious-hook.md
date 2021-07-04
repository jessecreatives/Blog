---
title: "React: 自作のusePreviousフックで前stateにアクセス"
excerpt: >-
  Reactでは、今より前のstateやpropsを獲得しようとする場合があるでしょう。classコンポーネントでは、componentDidUpdateがあるため、割と簡単に前のstateやpropsにアクセスできますが、functionコンポーネントではHookを利用する必要があります。
date: "2020-01-09"
thumb_img_path: images/useprevious_title.jpg
thumb_img_alt: "React: 自作のusePreviousフックで前stateにアクセス"
content_img_path: images/useprevious_title.jpg
content_img_alt: "React: 自作のusePreviousフックで前stateにアクセス"
seo:
  title: "React: 自作のusePreviousフックで前stateにアクセス"
  description: >-
    usePreviousフックを利用し、前の state にアクセルする方法を学習する。
  extra:
    - name: "og:type"
      value: article
      keyName: property
    - name: "og:title"
      value: "React: 自作のusePreviousフックで前stateにアクセス"
      keyName: property
    - name: "og:description"
      value: >-
        usePreviousフックを利用し、前の state にアクセルする方法を学習する。
      keyName: property
    - name: "og:image"
      value: images/useprevious_title.jpg
      keyName: property
      relativeUrl: true
    - name: "twitter:card"
      value: summary_large_image
    - name: "twitter:title"
      value: "React: 自作のusePreviousフックで前stateにアクセス"
    - name: "twitter:description"
      value: >-
        usePreviousフックを利用し、前の state にアクセルする方法を学習する。
    - name: "twitter:image"
      value: images/useprevious_title.jpg
      relativeUrl: true
layout: post
---

Photo by [Nick Fewings](https://unsplash.com/@jannerboy62?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/back-arrow?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

React では、今より前の state や props を獲得しようとする場合があるでしょう。class コンポーネントでは、componentDidUpdate があるため、割と簡単に前の state や props にアクセスできますが、function コンポーネントでは Hook を利用する必要があります。

今回は[React 公式サイト](https://reactjs.org/docs/hooks-faq.html#how-to-get-the-previous-props-or-state){:target="\_blank"}にも掲載されている「usePrevious」フック を利用し、前の state にアクセルする方法を学習していきましょう。

<hr>

### **useRef で前 state にアクセスしてみる**

現状 React には前 state を処理する Hook がないです。しかし、useRef を使えば、自分でそのような Hook を作れます。簡単なコンポーネントを書いて説明していきましょう。
![]({{site.baseurl}}images/usePrevious-before.png)
このコードをまずしっかり理解しておきましょう。

1. `const prevCountRef = useRef()`で`prevCountRef`という ref を定義します。`prevCountRef.current`値は`undefined`です。

2. `useEffect`で`count`という state の値を`prevCountRef.current`にパスします。

3. 2 でゲットした値を今度`prevCount`に与えます。ただし、**`useEffect`は全てのコンポーネントが mount/render されてから実行されるので、`const prevCount = prevCountRef.current`が実行される際、`useEffect`はまだ実行されていないです**。そのため、ここの`prevCount`の値は**`undefined`**です。これはこの方法で前 state をキャッチできるカギです。

このコードを実行すると、下図のような挙動を確認できます。
![]({{site.baseurl}}images/usePrevious.gif)

<hr>

### **usePrevious を作って、コードを整理する**

上記のコードで上手く動きましたが、自分でフックを作って、コードはもう少しすっきりさせましょう。
![]({{site.baseurl}}images/usePrevious-after.png)

<hr>

### **終わりに**

今回は自作の Hook でコンポーネントの前 state の処理をしてみました。重要ポイントは`useEffect`はコンポーネントが mount/render された後に実行されるところです。これを上手く利用し、前 state を処理できました。
