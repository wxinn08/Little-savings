# Little Savings · Firebase 双人版

## 部署
1. 解压本 ZIP。
2. 将 `little_savings` 文件夹内的全部文件上传并覆盖 GitHub 仓库中原本同名文件。
3. 等 GitHub Pages 部署完成后，重新打开原网址。

## 第一次使用
1. 你用自己的邮箱注册账号；如果以前已注册，直接登录。
2. 你女朋友在她自己的手机上，用她自己的邮箱注册账号。不要共用密码。
3. 女朋友注册后，页面会显示她的 UID。复制这个 UID。
4. 在 Firebase Console → Firestore Database → `spaces` → 你原本的空间文件 → `members` 数组，把女朋友的 UID 加进去。保留你自己的 UID，不要覆盖。
5. 女朋友退出再登录；你也刷新或重新登录。两人就会连接同一个空间。

## 重要
- 本版使用 Firebase Authentication 邮箱/密码登录和 Cloud Firestore。
- 不需要手动建立 `transactions` 或 `goals` 子集合；第一次新增记录/目标时会自动建立。
- 若登录后显示“账号已登录，但尚未加入共同储蓄空间”，代表该 UID 尚未加入 `spaces/{空间ID}/members`。
- 旧版 localStorage 中的演示数据不会自动迁移到云端。请先保留旧版备份；旧记录不会因部署新版本而自动上传。
- 目前账单由空间成员共同读取；请勿存放银行密码、身份证号码等敏感资料。上线前建议再收紧 Firestore Security Rules，限制每位成员只能新增自己的交易。
