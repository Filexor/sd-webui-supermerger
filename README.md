# sd-webui-supermerger
model merge extention for stable diffusion web ui

testing [new version] adding new features (https://github.com/hako-mikan/sd-webui-supermerger/tree/ver2)
機能追加した [new version]をテスト中です。 (https://github.com/hako-mikan/sd-webui-supermerger/tree/ver2)

updated 2023.01.20.2350(JST)
png infoがうまく保存できない問題を解決しました。
Problem solved where png info could not be saved properly.

日本語説明は後半にあります。

This an extension for [stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

This extension enables the model to be loaded for image generation without saving when the model is merged.
Models can be merged in block-by-block. In the past, merged models had to be saved once and deleted if they were not to your liking, but this extension saves time and prevents wear and tear on HDDs and SSDs.

See below for installation instructions

https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions

For more information on Merge Block Weighted, please refer to the following
https://github.com/bbc-mc/sdweb-merge-block-weighted-gui

usege

[merge] button: After merging, the model is loaded as a model for generation. **Note that a different model is loaded than the model information in the upper left corner. **(This will be reset when you re-select the model in the model selection screen in the upper left corner.

[gen] button: Generates an image using the settings in the text2image tab

[Merge and Gen] Merge and load models to generate images

[Save merged model] Save the currently loaded merged model.(A new merge is performed. This is because saving a loaded model saves it as a single-precision model.)

[Sequential Merge and Generation] Performs sequential merge image generation. For example, if you run the program with "0.25,0.5,0.75", it will generate images with the respective merge ratio.For block merge, enter 26 numbers separated by newlines and separated by commas
![xy_grid-0355-1880406603 0-merge, two ladies,green twintails,flat chest,lolita (long dress_1 3),(put  hands together_1 3),red pigtails,mirror,smile,look ea](https://user-images.githubusercontent.com/122196982/213196391-1a040bfa-1ade-409a-804f-427a3fb8bf8f.jpg)

About Cache
The cache is used to store models in memory to speed up sequential merges and other operations.
Cache settings can be configured from web-ui's setting menu.

This script uses some of the web-ui and mbw-merge scripts.

このextentionではモデルをマージした際、保存せずに画像生成用のモデルとして読み込むことができます。
これまでマージしたモデルはいったん保存して気に入らなければ削除するということが必要でしたが、このextentionを使うことでHDDやSSDの消耗を防ぐことができます。

階層別マージについては下記を参照してください

https://github.com/bbc-mc/sdweb-merge-block-weighted-gui

使い方

[merge]ボタン：マージした後、生成用モデルとして読み込みます。**左上のモデル情報とは違うモデルがロードされていることに注意してください。**左上のモデル選択画面でモデルを選択しなおすとリセットされます

[gen]ボタン:text2imageタブの設定で画像生成を行います

[Merge and Gen] ボタン：マージしたのち画像を生成します

[Save merged model]現在読み込まれているマージモデルを保存します(新規にマージを行います。これはロードされたモデルを保存すると単精度のモデルとして保存されるためです)

[Sequential Merge and Generation]連続マージ画像生成を行います。例えば「0.25,0.5,0.75」で走らせると、それぞれのマージ率で画像を生成します。seedを「-1」に設定している場合でも同じseedで生成します。
![xy_grid-0355-1880406603 0-merge, two ladies,green twintails,flat chest,lolita (long dress_1 3),(put  hands together_1 3),red pigtails,mirror,smile,look ea](https://user-images.githubusercontent.com/122196982/213196391-1a040bfa-1ade-409a-804f-427a3fb8bf8f.jpg)

キャッシュについて
モデルをメモリ上に保存することにより連続マージなどを高速化することができます。
キャッシュの設定はweb-uiのsettingから行ってください。

このスクリプトではweb-uiとmbw-mergeのスクリプトを一部使用しています

