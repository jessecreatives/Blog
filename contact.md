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
          - Inquiries about my work/blog post
          - Other
      - input_type: textarea
        name: message
        label: Message
        default_value: Your message
      - input_type: checkbox
        name: consent
        label: >-
          I understand that this form is storing my submitted information so I
          can be contacted.
    submit_label: Send Message
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
