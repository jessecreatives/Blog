---
title: "React: 超見つかりにくいミス"
excerpt: >-
  アロー関数の記述で誰でも一度は犯すミスがあります。これは非常に見つかりにくいため、直すのに相当時間がかかります。しかしその一方で、気付いたら笑うほどの単純なミスでもあります。
date: "2019-11-20"
thumb_img_path: images/trap_title.jpg
thumb_img_alt: "React: 超見つかりにくいミス"
content_img_path: images/trap_title.jpg
content_img_alt: "React: 超見つかりにくいミス"
seo:
  title: Basic Rules For Walking In The Mountains
  description: >-
    Hiking refers to difficult walking through dense forest, undergrowth, or
    bushes.
  extra:
    - name: "og:type"
      value: article
      keyName: property
    - name: "og:title"
      value: Basic Rules For Walking In The Mountains
      keyName: property
    - name: "og:description"
      value: >-
        Hiking refers to difficult walking through dense forest, undergrowth, or
        bushes.
      keyName: property
    - name: "og:image"
      value: images/6.jpg
      keyName: property
      relativeUrl: true
    - name: "twitter:card"
      value: summary_large_image
    - name: "twitter:title"
      value: Basic Rules For Walking In The Mountains
    - name: "twitter:description"
      value: >-
        Hiking refers to difficult walking through dense forest, undergrowth, or
        bushes.
    - name: "twitter:image"
      value: images/6.jpg
      relativeUrl: true
layout: post
---

Photo by [Nick Fewings](https://unsplash.com/@jannerboy62?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) on [Unsplash](https://unsplash.com/s/photos/back-arrow?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)

アロー関数の記述で誰でも一度は犯すミスがあります。これは非常に見つかりにくいため、直すのに相当時間がかかります。しかしその一方で、気付いたら笑うほどの単純なミスでもあります。

では、早速実例をあげて説明していきましょう。下図のコードの問題点はどこですか。答えを見ず、まず自分で探してみてください（ヒント：エラーメッセージは"Expected an assignment or function call and instead saw an expression"です）。
![]({{site.baseurl}}images/react-error.png)

エラーメッセージは、これは関数であるべきなのに、関数には見えないね、との意味です。では、なぜ関数じゃないでしょうか。

問題は、この「関数」はちゃんと値を返していないことです。アロー関数で値を返す時の記法は２パターンがあります：

```
... => (
    // JSX
)
```

または、

```
... => {
    return (
        // JSX
    );
}
```

です。

しかし、例のコードは、上記のどちらの記法でもなかったのです。これがエラーの原因です。意外と細かい部分ではありますが、これで苦労するエンジニアをしばしば見かけますので、十分に気をつけましょう！
