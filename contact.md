---
title: お問い合わせ
hide_title: false
sections:
  - section_id: contact-form
    type: section_form
    content: |
      下記のフォームを記入した上で、ご送信ください。
    form_id: contactForm
    form_action: /thank-you
    form_fields:
      - input_type: text
        name: name
        label: 氏名
        default_value: 氏名
        is_required: true
      - input_type: email
        name: email
        label: メールアドレス
        default_value: メールアドレス
        is_required: true
      - input_type: select
        name: subject
        label: タイトル
        default_value: 選択してください
        options:
          - Jesseと提携したい
          - Jesseと繋がりたい
          - Jesseのブログ・作品に興味がある
          - その他
      - input_type: textarea
        name: message
        label: メッセージ
        default_value: メッセージ（250文字以内）
      - input_type: checkbox
        name: consent
        options: []
        label: 送信ボタンを押すことは、個人情報の取扱いについてに同意したとみなします。
    submit_label: 送信する
seo:
  title: Contact
  description: This is the contact page
  extra:
    - name: 'og:type'
      value: website
      keyName: property
    - name: 'og:title'
      value: Contact
      keyName: property
    - name: 'og:description'
      value: This is the contact page
      keyName: property
    - name: 'twitter:card'
      value: summary
    - name: 'twitter:title'
      value: Contact
    - name: 'twitter:description'
      value: This is the contact page
layout: advanced
---
