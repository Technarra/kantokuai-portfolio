# KantokuAI — 画面で見る動画制作の流れ

[READMEへ戻る](../README.md) · [開発で考えたこと（詳細）](decisions.md) · [動画制作の流れとAIの分担](architecture.md)

企画から書き出しまでの10画面を、操作の順に紹介します。画像を開くと、元の解像度で見られます。

## 1. 企画と台本

### ① 伝えたいことを対話で決める

AIの質問に答えたり、選択肢を選んだりしながら、動画で伝える内容を具体的にします。毎回文章を考えて入力しなくても進められるよう、返答の候補を選択肢として出しています。工場の紹介を題材にした架空のデモです。

<a href="../assets/kantokuai-ui-chat.png"><img src="../assets/kantokuai-ui-chat.png" width="360" alt="工場紹介のデモで、AIの質問に答えながら企画を決める画面"></a>

### ② シーンごとのセリフを確認する

対話から作った台本を、シーン単位で読み直します。セリフとシーンを制作データとして持つので、そのまま撮影と編集につながります。

<a href="../assets/kantokuai-ui-script.png"><img src="../assets/kantokuai-ui-script.png" width="360" alt="架空の工場デモの台本を、シーン単位で確認する画面"></a>

### ③ 直したいところを選んで指示する

セリフ、シーン、撮影方法、画角・構図、場所・背景、見本画像などから直したい対象を選び、AIに修正を頼む入口です。生成した後も、自分の意図に合わせて直せるようにしています。

<a href="../assets/kantokuai-ui-scene-revision.png"><img src="../assets/kantokuai-ui-scene-revision.png" width="360" alt="シーンの修正対象を選ぶ画面"></a>

## 2. 撮影

### ④ 撮り方を選ぶ

「自分の音声で撮る」「スマホから選択」「AI音声で始める」の3つから選びます。自分で撮る場合は、動画全体の撮影プランと見本画像を確認してからカメラへ進みます。この画像は、撮影プランがまだ入っていない状態です。

<a href="../assets/kantokuai-ui-capture-entry.png"><img src="../assets/kantokuai-ui-capture-entry.png" width="360" alt="自分の音声・スマホの動画・AI音声から撮り方を選ぶ画面"></a>

### ⑤ カンペの読みやすさを調整する

文字の大きさと流れる速さを、表示例を見ながら調整します。AIが台本を作っても、話す人が読みにくければ撮影は進まないので、読み方は本人が決められるようにしました。

<a href="../assets/kantokuai-ui-recording-settings.png"><img src="../assets/kantokuai-ui-recording-settings.png" width="360" alt="カンペの文字の大きさとスクロールの速さを設定する画面"></a>

### ⑥ カンペを見ながら撮影する

カメラ画面に台本を重ねて表示するので、台本を覚えずに、自分の声で話せます。実機での撮影画面です（工場のデモとは別の説明動画）。

<a href="../assets/kantokuai-ui-camera.png"><img src="../assets/kantokuai-ui-camera.png" width="360" alt="説明動画の台本をカンペとして重ねた、実機の撮影画面"></a>

## 3. 編集と書き出し

### ⑦ 字幕とカットを時間軸で調整する

話した内容から作った字幕とカット、追加の素材を、時間軸で確認して直します。言葉の意味の判断はAI、元の動画との時間の対応はコードが担当し、仕上がりは本人が確かめます。実機での編集画面です。

<a href="../assets/kantokuai-ui-editor.png"><img src="../assets/kantokuai-ui-editor.png" width="360" alt="説明動画の字幕と補足素材を、時間軸で編集する実機の画面"></a>

### ⑧ AIの素材提案を確認する

発話に合う補足素材の候補と、提案の理由を見て、使うかどうかを決めます。候補は採用・取り消し・作り直しができます。

<a href="../assets/kantokuai-ui-proposal.png"><img src="../assets/kantokuai-ui-proposal.png" width="360" alt="補足素材の内容と提案理由を確認する実機の画面"></a>

### ⑨ セリフに合わせて素材を加える

セリフごとに、撮影する・写真を加える・見本画像を使う、から素材の追加方法を選びます。

<a href="../assets/kantokuai-ui-add-material.png"><img src="../assets/kantokuai-ui-add-material.png" width="360" alt="セリフに対応する素材の追加方法を選ぶ画面"></a>

### ⑩ 書き出して共有する

書き出しが終わると、投稿用の文章と共有先が表示され、そのままSNSへ投稿できます。動画の合成は端末の中で行います。

<a href="../assets/kantokuai-ui-export-complete.png"><img src="../assets/kantokuai-ui-export-complete.png" width="360" alt="書き出し完了後に、投稿用の文章と共有先を表示する画面"></a>

## 撮影した環境

①〜⑤・⑨・⑩はSimulator（iPhone 17 Pro / iOS 26.5）、⑥〜⑧は実機の画面です。いずれも2026年9月の開発版で、App Storeで配信中の版とは表示が異なる部分があります。画面の画像は編集していません。

## 画面内の参考素材の出典

- ④の金属加工の写真：byrev, [Cutting iron](https://commons.wikimedia.org/wiki/File:Cutting_iron.jpg)（CC0 1.0）
- ⑨・⑩の金属加工の映像：Daniel Smyth, [A machine is cutting metal with a metal cutting tool](https://www.pexels.com/video/a-machine-is-cutting-metal-with-a-metal-cutting-tool-9033891/)（[Pexelsの利用条件](https://www.pexels.com/license/)に基づいて使用）

参考素材は、自分で撮影した工場や顧客の設備ではありません。アプリの説明用の画面の中でのみ使っています。
