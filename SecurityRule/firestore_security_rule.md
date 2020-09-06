# Firestore Security Rule

## Security Rile
### Method
* READ
  * get
  * list
* WRITE
  * create
  * update
  * delete

### Security Rule file
```yaml
service cloud.firestore {
  match /databases/{database}/documents {

    // A read rule can be divided into get and list rules
    match /cities/{city=**} {
      allow get: if <condition>;
      allow list: if <condition>;
    }

    // A write rule can be divided into create, update, and delete rules
    match /cities/{city=**} {
      allow create: if <condition>;
      allow update: if <condition>;
      allow delete: if <condition>;
    }

  }
}
```
> memo: ルールが任意の深い階層に適用されるようにするには、再帰ワイルドカード構文、{name=**} を使用する。

.rules
```
firebase deploy --only firestore:rules
```

## Reference
* [Medium](https://medium.com/google-cloud-jp/firestore3-9518331f8748)
* [Firebase: Firebase Security Rules](https://firebase.google.com/docs/rules)
* [Firebase: Security Rules language](https://firebase.google.com/docs/rules/rules-language)
* [Firebase: Structuring Cloud Firestore Security Rules](https://firebase.google.com/docs/firestore/security/rules-structure)
* [Firebase: Writing conditions for Cloud Firestore Security Rules](https://firebase.google.com/docs/firestore/security/rules-conditions)
* [Qiita](https://qiita.com/sgr-ksmt/items/a7bda48535033f6a4b68)
* [Ginco Tech Blog](https://tech.ginco.io/post/firestore-rules/)
* [Firestore セキュリティルール ～入門編～](https://rightcode.co.jp/blog/information-technology/firestore-security-rules-introduction)
---
### VSCode Syntax Highlighting for Firestore Security Rule
* [toda/Firebase](https://marketplace.visualstudio.com/items?itemName=toba.vsfire)


