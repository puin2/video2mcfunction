# Video-2-Mcfunction.py


動画をカスタムフォントとして使える形で出力するpythonスクリプトです。


## 前提
- python 3.10.x, [ffmpeg](https://ffmpeg.org)
- `pip install -r requirements.txt`
  - ffmpeg-python
  - numpy
  - opencv-python

## 使い方
コマンドプロンプトから以下を実行すると、同フォルダ内のV2M_outputフォルダにリソース/データパックが出力されます。</br></br>
`python v2m.py -i '動画ファイルのパス' -n 'リソース/データパックで使用するネームスペース'`
 - ネームスペースは全て小文字になります。
 - `-r`でスケールされる解像度を変更することが出来ます。 最大=256
   - 設定した値が縦か横で最大になるようにアスペクト比を維持してスケールされます。</br>
 
## 生成物
最初に</br>
`function ネームスペース:init`</br>
を実行した後、以下をtickで実行してください。</br>
`function ネームスペース:play`  または  `function ネームスペース:reverse`(逆再生)</br></br>
表示側(看板、titleコマンドなど)は↓を使用すると表示できます。 (tickで実行しないと更新されません。)</br>
`{"nbt":"playing[0]","storage":"ネームスペース:","font":"ネームスペース:title","interpret":true,"color":"white"}`

- フォントはtitle以外にもsign,other,reverseが利用できます。
  - `title` ascent:40 height:80 
  - `sign` ascent:47 height:54  看板のText4用。
  - `other` ascent:54 height:54
  - `reverse` ascent:54 height:54  otherを逆順に並べ替えたもの。
