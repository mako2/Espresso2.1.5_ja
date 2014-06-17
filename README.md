Espresso2.1.5_ja
============
これは2ちゃんねるの新・Mac板 [Espresso : Web統合開発環境 【MacRabbit】](http://anago.2ch.net/test/read.cgi/mac/1321757964/) スレッドで派生した Espresso2(2.1.5) のローカライズ(日本語化)プロジェクトです。  
[POEditor](https://poeditor.com/) の無料アカウントで作業していましたが、アカウントを半年放置するとプロジェクトごと削除されるようで…ローカライズ専用サービスだったので作業はしやすかったのですが Github に移行することにしました。

現状この README.md さえも不完全ですが、とりあえず形にすることを目標としたのでご理解下さい。


ローカライズが必要なファイル
----------------------

ローカライズが必要なファイルは、Espresso.app を右クリックして「パッケージの内容を表示」で確認できます。  

`Espresso.app/Contents/Resources/`

上記 Resources フォルダ 内の English.lproj フォルダが主なローカライズ作業の対象となります。

まず English.lproj をコピーして ja.lproj と名称を変更し中のファイルをローカライズしていきます。  
ローカライズが必要なのは以下のファイルのようです。  
Espresso.app/Contents/Resources/ja.lproj

- EKSyntaxDebugger.nib
- EKSyntaxInspector.nib
- Espresso.nib
- EspressoActivation.nib
- EspressoActivationTrialPanel.nib
- EspressoPreferences.nib
- ESSearchSource.nib
- PublishSettings.nib
- server-browser.sidebar.permissions.nib
- ServerBookmarkEditor.nib
- StyleFavorites.nib
- StyleFontPanel.nib
- StyleOverrideInspector.nib
- StyleOverridePanel.nib
- SyntaxThemePreferences.nib
- CSSTools.strings
- EditorKit.strings  / Espresso.nib と連動 / Clear Menu
- ESPreview.strings
- FSClient.strings
- InfoPlist.strings
- Localizable.strings
- MRApplicationUtilities.strings
- EspressoHelpBook (ヘルプ用ファイル)

- - -
名称変更した ja.lproj と同じディレクトリにある以下のファイルもローカライズをする必要がありますが、優先順位は2番目です。  

- GotoLine.nib
- MRProgressPanel.nib
- PlugInPreferences.nib
- ProjectManager.nib
- Snippets.nib
- SugarUpdater.nib
- TEAEnterAbbreviationSheet.nib
- UserSnippetsManager.nib
- Welcome.nib
- XRayInspector.nib
- Tabs.strings / Espresso.nib と連動

以下は再コンパイル出来なかったり編集の必要が無いファイルです。

- ColorPicker.nib / 再コンパイル不可
- ESStyleMultiPartItems.nib / 再コンパイル不可
- ESTestCSSTool.nib / 編集箇所無し
- StyleEditors.nib / 編集箇所無し
- SUStatus.nib / 元々のインターフェイスが意味不明なので放置


- - -
ja.lproj と同じディレクトリにあるプラグインもパッケージの構造をしているので、右クリックして「パッケージの内容を表示」で必要なファイルをローカライズしていきます。優先順位は3番目です。  
例) `Espresso.app/Contents/Resources/EspressoPrivate.espressoplugin/Contents/Resources/ja.lproj` (en.lproj をコピーして名称変更)

- EspressoPrivate.espressoplugin


以下は編集の必要が無いプラグインです。

- Selectors.espressoplugin
- Snippets.espressoplugin
- SyntaxTheme.espressoplugin

- - -
Resources と同じディレクトリにある SharedSupport の中にもプラグインがあるのでこちらもローカライズ作業を行います。  
Espresso.app/Contents/SharedSupport/Plug-Ins

- CSS.espressoplugin
- Markdown.espressoplugin
- TEA for Espresso.espressoplugin
- XML-and-HTML.espressoplugin

以下は編集の必要が無いプラグインです。

- Apache.espressoplugin
- JavaScript.espressoplugin
- PHP.espressoplugin
- Python.espressoplugin
- Regex.espressoplugin
- Ruby.espressoplugin


ローカライズの手順
--------------

ローカライズの手順を解説しています。

### 必要なアプリケーション

Github を利用しますのでデスクトップで作業するには Githubクライアントが必要です。公式アプリの他、サードパーティー製の有料のものもあります。  
ローカライズ作業は iLocalize.app を使用します。

- [Github.app](https://mac.github.com) / 無料の公式 Github クライアント
- [iLocalize.app](https://itunes.apple.com/jp/app/ilocalize/id437165919?mt=12) / 無料

([nibTranslate Light.app](https://itunes.apple.com/jp/app/nibtranslate-light/id419607106?mt=12) は使いやすいのですが、無料版だと書き出し機能が無いので今回は iLocalize.app を使用します。)

### iLocalize の使い方

1. 拡張子が .ilocalize のショートカットをダブルクリックすると iLocalize.app が起動します。 
2. ウィンドウ左上のプルダウンメニューを「日本語」にします。
3. 任意のファイルを選択して日本語に翻訳します。

####編集してはいけない状態および英文

以下の英文は翻訳しないでください。（一応該当箇所はロックしています）

1. 状態が = のもの(黒丸の中にイコール)
2. Text Cell
3. OtherViews
4. Radio
5. Window

### ローカライズのルール

- 半角記号はそのまま使用。 例) : や ; など。? などの感嘆符、疑問符は全角にしました。
- 翻訳しない半角英数の前後は半角スペースを入れる。ただし単語の前が句読点や半角記号で終わる場合はそのままとする。 例) クリックすると検索結果を消去。Option + クリックで検索条件を変更

### ローカライズする .iLocalize ファイル
拡張子が .iLocalize のファイルをローカライズします。作業しやすいようにトップディレクトリにショートカットを用意しています。  

- Resources>ja_lproj.ilocalize
- Resources.ilocalize
- Resources>EspressoPrivate_espressoplugin.ilocalize
- SharedSupport>Plug-Ins>CSS.ilocalize
- SharedSupport>Plug-Ins>Markdown.ilocalize
- SharedSupport>Plug-Ins>TEA.ilocalize
- SharedSupport>Plug-Ins>XML.ilocalize


インターフェイスの修正
-----------------

以下はローカライズしたテキストが切れるなどの不具合があるので修正が必要なファイルです。随時追加していきます。

- Espresso.app/Contents/Resources/EspressoPreferences.nib
- Espresso.app/Contents/Resources/SugarUpdater.nib
- Espresso.app/Contents/Resources/GotoLine.nib
- Espresso.app/Contents/Resources/ProjectManager.nib
- Espresso.app/Contents/Resources/UserSnippetsManager.nib
- Espresso.app/Contents/Resources/XRayInspector.nib
- Espresso.app/Contents/Resources/MRProgressPanel.nib
- Espresso.app/Contents/Resources/Welcome.nib
- Espresso.app/Contents/Resources/EKSyntaxInspector.nib
- Espresso.app/Contents/Resources/ja.lproj/ServerBookmarkEditor.nib
- Espresso.app/Contents/Resources/ja.lproj/StyleFontPanel.nib


ローカライズの下準備
---------------

ここはローカライズ作業に直接関係ないので読み飛ばしても構いません。

### 拡張子が .nib のファイル
このファイルは簡単に言うとGUIファイルです。  
ほとんどのnibファイルはコンパイルされていてそのままでは編集できないので、[NibUnlocker.app](http://www.charlessoft.com) を使って再コンパイルします。
再コンパイルされたファイルはxib形式で保存され Xcode で編集が可能になります。

次に生成されたxibファイルを Xcode でnibファイルとして別名保存します。（Xcode が落ちる場合は、名称を変えてxibファイルとして保存 → それをnibファイルとして別名保存 → 名称を元に戻す、これで上手くいきます。）

### 拡張子が .strings のファイル
このファイルはローカライズ専用のファイルですのでそのままで編集出来ます。

### iLocalize に読み込むための準備
iLocalize.app は、２つの言語ファイル（フォルダ）を読み込んで比較しながら作業をするように出来ているようです。ですので Github にある全てのローカライズ用フォルダは English.lproj と ja.lproj の様に2つの言語フォルダで構成されています。
