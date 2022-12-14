README_ja

ユニティちゃんトゥーンシェーダー Ver.2.0.4

「ユニティちゃんトゥーンシェーダー」は、セル風3DCGアニメーションの制作現場での要望に応えるような形で設計された、映像志向のトゥーンシェーダーです。

ユニティちゃんトゥーンシェーダーVer.2.0では、従来の機能に加えて大幅な機能強化を行いました。
Ver.1.0でできる絵づくりをカバーしつつ、さらに高度なルックが実現できるようになっています。

【ターゲット環境】
Unity5.6.x もしくはそれ以降が必要です。
本パッケージは、Unity5.6.5p1で作成されています。

【iOS/OSX METALで使用する際の注意】
iOS/OSX METALで使用する場合、CullMode=OFF（両面表示）の時に、正しい表示が出来ない場合があります。
その場合、メッシュを両面に貼って、それぞれにCullMode=Back（背面カリング）/CullMode=Front（正面カリング）のマテリアルを設定するようにしてください。

【提供ライセンス】
「ユニティちゃんトゥーンシェーダーVer.2.0」は、UCL2.0（ユニティちゃんライセンス2.0）で提供されます。
ユニティちゃんライセンスについては、以下を参照してください。
http://unity-chan.com/contents/guideline/


【インストールの注意】
UTS2_ShaderOnly_v2.0.4.unitypackage
新規インストールは、Unityにそのまま本パッケージをD&Dすればインストールされます
上書きインストール時には、コードが全面的に改修されていますので、注意が必要です。
１．元のプロジェクトのバックアップをとっておく
２．Unityでプロジェクトを開き、新規シーンを作成して開いておく。
３．元のトゥーンシェーダーが入っているフォルダ（Assets/Toon/Shader）をUnity上から削除する。
４．本パッケージをUnityにD&Dする。

まず元のシェーダーを消した後で、すぐに新しいシェーダーをインストールすれば、既存のマテリアルへのリンクは途切れないので、そちらでやってみてください。

個人でみられる範囲でバグチェックはしていますが、何か不具合があったらご連絡よろしくお願いします。


【新規】
2018/03/26
UTS_EdgeDetection.unitypackage
ポストエフェクトタイプのエッジ抽出フィルタです。
元々はUnityのStandard Assetsにあったものを改造したフィルタ3つに加えて、新規に作成したSobel Color Filterが追加されています。
Sobel Color Filterを使うことで、効果的にトゥーンラインエッジを強調し、セル画時代の色トレス風の雰囲気を出すことができます。
本ポストエフェクトは、ポストエフェクトスタックの前に入れるとよいと思います。

2018/02/09：2.0.4：ターゲット環境を正式にUnity5.6.x以降としました。（Unity2018.1にも対応しています）
　　　　　　　　　 コードの全面的な改修＆バグ修正の他、以下の仕様を新規に追加しました。

●Phong Tessellation対応
　対応部分のコードは、Nora氏の https://github.com/Stereoarts/UnityChanToonShaderVer2_Tess を参考にさせていただきました。
　Tessellationは、使えるプラットフォームが限られている上に、かなりパワフルなPC環境を要求しますので、覚悟して使ってください。
　想定している用途は、パワフルなWindows10/DX11のマシンを使って、映像＆VR向けに使用することです。
　Light版とあるものは、ライトをディレクショナルライト１灯に制限した代わりに軽量化したバリエーションです。
●Positionスケーリングベースのアウトラインを搭載。
　従来の法線反転方式だとアウトラインが切れてしまう、キューブのようなモデルに綺麗にアウトラインが出せます。
●クリッピング系シェーダーでアウトラインのアルファ抜きに対応。
　アルファ付きテクスチャと組み合わせた時に、背面から見てもアウトラインポリゴンがアルファに従って抜けるようにした。
●アウトライン用テクスチャ（Outline_Tex）の搭載。
●ハイカラー用テクスチャ（HiColor_Tex）の搭載。
●PostProcessingStackと一緒に使うことを前提に、エミッシブカラー（Emissive_Color）およびエミッシブ用テクスチャ（Emissive_Tex）を搭載。
　エミッシブカラー側でHDR値が設定できるので、PostProcessingStackのブルームエフェクトと組み合わせることで、エミッシブ部分を光らせることができるようになった。

　※今回搭載された新規テクスチャに関しても、今まで通り、必要なければ使わなくても問題ないようになっています。

【過去の修正履歴】
2017/06/25：2.0.3：マニュアル修正。【iOS/OSX METALで使用する際の注意】を追加。
2017/06/19：2.0.3：Set_HighColorMask、Set_RimLightMaskの追加。機能強化の結果、Set_HighColorPositionは廃止。
2017/06/09：2.0.2：Nintendo Switch、PlayStation 4に正式対応。モバイル軽量版の追加。その他機能強化。
2017/05/20：2.0.1：TransClipping系シェーダーのブレンド仕様変更とリムライトに調整機能追加。
　　　　　　　　　 上の仕様変更に伴い、トランスペアレント系シェーダーを２つ追加。
　　　　　　　　　（ToonColor_DoubleShadeWithFeather_Transparent、ToonColor_ShadingGradeMap_Transparent）
2017/05/07：2.0.0：最初のバージョン


最新バージョン：2.0.4
最終リリース日：2018.02.09
カテゴリー：3D
形式：zip
