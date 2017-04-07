---
title: "-clr (共通言語ランタイムのコンパイル) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLR"
  - "VC.Project.VCNMakeTool.CompileAsManaged"
  - "VC.Project.VCCLCompilerTool.CompileAsManaged"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe コンパイラ, 共通言語ランタイムのオプション"
  - "-clr コンパイラ オプション [C++]"
  - "clr コンパイラ オプション [C++]"
  - "/clr コンパイラ オプション [C++]"
  - "C++ マネージ拡張, コンパイル"
  - "共通言語ランタイム, /clr コンパイラ オプション"
ms.assetid: fec5a8c0-40ec-484c-a213-8dec918c1d6c
caps.latest.revision: 72
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 72
---
# /clr (共通言語ランタイムのコンパイル)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーションおよびコンポーネントで、共通言語ランタイム \(CLR\) の機能を使用できるようにします。  
  
## 構文  
  
```  
/clr[:options]  
```  
  
## 引数  
 `options`  
 次の 1 つまたは複数のスイッチをコンマで区切って指定します。  
  
 **\/clr**  
 アプリケーションのメタデータを作成します。 このメタデータは、他の CLR アプリケーションで使用できます。また、このメタデータによって、他の CLR コンポーネントのメタデータの型とデータをアプリケーションで使用できるようになります。  
  
 詳細については、次のトピックを参照してください。  
  
 「[混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)」および「  
  
 [方法: \/clr に移行する](../../dotnet/how-to-migrate-to-clr.md)。  
  
 **\/clr:pure**  
 ネイティブの実行可能コードを含まない、Microsoft Intermediate Language \(MSIL\) のみの出力ファイルを作成します。 ただし、MSIL にコンパイルされたネイティブ型が含まれることもあります。  
  
 詳細については、「[純粋なコードと検証可能なコード](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
 \/clr:pure の使用は推奨されていません。 コンパイラの将来のバージョンでこのオプションがサポートされない可能性があります。 純粋 MSIL にする必要があるコードは、C\# に移植することをお勧めします。  
  
 **\/clr:safe**  
 ネイティブの実行可能コードを含まない、MSIL のみの検証可能な出力ファイルを作成します。**\/clr:safe** によって、検証の診断 \([PEVerify ツール \(Peverify.exe\)](../Topic/Peverify.exe%20\(PEVerify%20Tool\).md)\) が有効になります。  
  
 詳細については、[検証可能なタイプ セーフ コードの作成](http://msdn.microsoft.com/ja-jp/d18f10ef-3b48-4f47-8726-96714021547b)に関する記事を参照してください。  
  
 \/clr:safe の使用は推奨されていません。 コンパイラの将来のバージョンでこのオプションがサポートされない可能性があります。 検証可能な純粋 MSIL にする必要があるコードは、C\# に移植することをお勧めします。  
  
 **\/clr:noAssembly**  
 アセンブリ マニフェストを出力ファイルに挿入できないことを指定します。 既定では、**noAssembly** オプションはオフです。  
  
 **noAssembly** オプションは使用されなくなりました。 代わりに、[\/LN \(MSIL モジュールの作成\)](../../build/reference/ln-create-msil-module.md) を使用してください。  
  
 マニフェストにアセンブリ メタデータがないマネージ プログラムを、*モジュール*と呼びます。**noAssembly** オプションは、モジュールを生成するときのみ使用できます。[\/c](../../build/reference/c-compile-without-linking.md) と **\/clr:noAssembly** を使用してコンパイルする場合は、リンカーのフェーズで [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) オプションを指定してモジュールを作成します。  
  
 Visual C\+\+ 2005 より前のバージョンでは、**\/clr:noAssembly** には **\/LD** が必要です。 現在は、**\/clr:noAssembly** を指定すると **\/LD** が暗黙的に指定されるようになっています。  
  
 **\/clr:initialAppDomain**  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] アプリケーションを CLR の Version 1 で実行できるようにします。**initialAppDomain** を使用する場合は、Microsoft サポート Web サイトの [Visual C\+\+ コンポーネントのマネージ拡張を使用する場合の AppDomainUnloaded 例外のバグ](http://go.microsoft.com/fwlink/?LinkID=169465)に関するページに記載されている問題が発生する可能性があります。  
  
 CLR の Version 1 では ASP.NET をサポートしていないため、**initialAppDomain** を使用してコンパイルされたアプリケーションは、ASP.NET を使用しているアプリケーションでは使用しないでください。  
  
 **\/clr:nostdlib**  
 既定の \\clr ディレクトリを無視するようにコンパイラに指示します。 System.dll などの DLL の複数のバージョンを含めると、コンパイラはエラーを生成します。 このオプションを使用すると、コンパイル時に使用する特定のフレームワークを指定できます。  
  
## 解説  
 マネージ コードは、CLR によって検査および管理できるコードです。 マネージ コードはマネージ オブジェクトにアクセスできます。 詳細については、「[\/clr の制約](../../build/reference/clr-restrictions.md)」を参照してください。  
  
 マネージ型を定義および使用するアプリケーションの開発方法については、「[Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)」を参照してください。  
  
 **\/clr** を使用してコンパイルされたアプリケーションには、マネージ データがある場合とない場合があります。  
  
 マネージ アプリケーションでのデバッグを有効にするには、「[\/ASSEMBLYDEBUG \(DebuggableAttribute の追加\)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)」を参照してください。  
  
 ガベージ コレクトされたヒープでインスタンス化されるのは CLR 型のみです。 詳細については、「[Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。 関数をネイティブ コードにコンパイルするには、`unmanaged` プラグマを使用します。 詳細については、「[マネージ、アンマネージ](../../preprocessor/managed-unmanaged.md)」を参照してください。  
  
 既定では、**\/clr** は無効です。**\/clr** が有効な場合は **\/MD** も有効です。 詳細については、「[\/MD、\/MT、\/LD \(ランタイム ライブラリの使用\)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。**\/MD** を使用すると、動的にリンクされるマルチスレッド バージョンのランタイム ルーチンが標準ヘッダー \(.h\) ファイルから選択されるようになります。 マネージ プログラミングでマルチスレッドが必要なのは、CLR のガベージ コレクターが、補助スレッドでファイナライザーを実行するためです。  
  
 **\/c** を使用してコンパイルする場合は、[\/CLRIMAGETYPE](../Topic/-CLRIMAGETYPE%20\(Specify%20Type%20of%20CLR%20Image\).md) を使用して、結果として出力されるファイルの CLR 型 \(IJW、safe、または pure\) を指定することができます。  
  
 **\/clr** は **\/EHa** を暗黙的に指定するため、**\/clr** では他の **\/EH** オプションを指定できません。 詳細については、「[\/EH \(例外処理モデル\)](../../build/reference/eh-exception-handling-model.md)」を参照してください。  
  
 ファイルの CLR イメージのタイプを判断する方法については、「[\/CLRHEADER](../../build/reference/clrheader.md)」を参照してください。  
  
 リンカーの特定の呼び出しに渡されるすべてのモジュールは、同じランタイム ライブラリ コンパイラ オプション \(**\/MD** または **\/LD**\) を使用してコンパイルされている必要があります。  
  
 [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) リンカー オプションを使用して、アセンブリにリソースを埋め込みます。[\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)、[\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)、および [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) の各リンカー オプションでも、アセンブリの作成方法をカスタマイズできます。  
  
 **\/clr** が使用されるときは、`_MANAGED` シンボルは 1 に定義されます。 詳細については、「[定義済みマクロ](../../preprocessor/predefined-macros.md)」を参照してください。  
  
 最初にネイティブなオブジェクト ファイルのグローバル変数が \(実行可能ファイルが DLL の場合は DllMain の実行中に\) 初期化され、その後でマネージ セクションのグローバル変数が \(いずれかのマネージ コードが実行される前に\) 初期化されます。`#pragma`[init\_seg](../../preprocessor/init-seg.md) は、マネージ カテゴリ内およびアンマネージ カテゴリ内での初期化の順序にのみ影響します。  
  
 **\/clr:safe** を使用してコンパイルすることは、C\# などの言語で [\/platform:anycpu](../Topic/-platform%20\(C%23%20Compiler%20Options\).md) を使用してコンパイルすることに似ています。  
  
## 安全なイメージと純粋なイメージ  
 純粋なイメージは C ランタイム \(CRT\) ライブラリの CLR バージョンを使用します。 ただし、CRT は検証できないので、**\/clr:safe** を使用したコンパイルでは CRT は使用できません。 詳細については、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」を参照してください。  
  
 純粋なイメージに表示できないネイティブ コードには、インライン アセンブリ、[setjmp](../../c-runtime-library/reference/setjmp.md)、[longjmp](../../c-runtime-library/reference/longjmp.md) などがあります。  
  
 純粋なイメージまたは安全なイメージの各エントリ ポイントはマネージになります。**\/clr** を使用してコンパイルすると、エントリ ポイントはネイティブになります。 詳細については、「[\_\_clrcall](../../cpp/clrcall.md)」を参照してください。  
  
 **\/clr:safe** を使用してコンパイルすると、変数は既定で [appdomain](../Topic/appdomain.md) になり、プロセスごとに設定できません。**\/clr:pure** を使用すると、**appdomain** が既定になりますが、[process](../../cpp/process.md) 変数を使用できます。  
  
 **\/clr** または **\/clr:pure** を使用してコンパイルされた 32 ビットの .exe ファイルを 64 ビット オペレーティング システムで実行すると、アプリケーションは WOW64 で実行されるため、32 ビット アプリケーションを 64 ビット オペレーティング システム上の 32 ビット CLR で実行できます。 既定では、**\/clr:safe** を使用してコンパイルされた .exe ファイルは、64 ビット オペレーティング システムを実行しているコンピューターの 64 ビット CLR で実行されます  \(32 ビット オペレーティング システムでは同じ .exe ファイルが 32 ビット CLR で実行されます\)。 ただし、安全なアプリケーションでは 32 ビット コンポーネントを読み込むこともできます。 この場合、オペレーティング システムの 64 ビット サポートで実行している安全なイメージで 32 ビット アプリケーションを読み込もうとすると失敗します \(BadFormatException\)。 安全なイメージが 64 ビット オペレーティング システムで 32 ビット イメージを読み込んでも失敗せずに実行を継続できるようにするには、[\/CLRIMAGETYPE](../Topic/-CLRIMAGETYPE%20\(Specify%20Type%20of%20CLR%20Image\).md) を使用してメタデータ \(.corflags\) を変更し、WOW64 で実行するようにマークする必要があります。 コマンド ラインの例を次に示します \(独自のエントリ シンボルと置き換えてください\)。  
  
 **cl \/clr:safe t.cpp \/link \/clrimagetype:pure \/entry:?main@@$$HYMHXZ \/subsystem:console**  
  
 装飾名を取得する方法については、「[装飾名](../Topic/Decorated%20Names.md)」を参照してください。 64 ビット プログラミングの詳細については、「[64 ビット用プログラムの構成](../../build/configuring-programs-for-64-bit-visual-cpp.md)」を参照してください。 純粋な CLR コードの使用の詳細については、「[方法: \/clr:pure に移行する](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)」と「[純粋なコードと検証可能なコード](../../dotnet/pure-and-verifiable-code-cpp-cli.md)」を参照してください。  
  
## メタデータと名前のないクラス  
 名前のないクラスは、メタデータに `$UnnamedClass$`*crc\-of\-current\-file\-name*`$`*index*`$` のような名前で表示されます。この *index* は、コンパイル時に名前のないクラスに与えられる連続番号です。 次のコードの例では、名前のないクラスをメタデータに生成します。  
  
```  
// clr_unnamed_class.cpp  
// compile by using: /clr /LD  
class {} x;  
```  
  
 メタデータを表示するには、ildasm.exe を使用します。  
  
## C\+\+ マネージ拡張  
 Visual C\+\+ では、**\/clr:oldsyntax** オプションがサポートされなくなっています。 このオプションは Visual Studio 2005 で推奨されなくなりました。 C\+\+ でのマネージ コードの記述でサポートされている構文は、C\+\+\/CLI です。 詳細については、「[Component Extensions for Runtime Platforms](../../windows/component-extensions-for-runtime-platforms.md)」を参照してください。  
  
 C\+\+ のマネージ拡張を使用するコードを使用している場合は、移植して C\+\+\/CLI 構文を使用することをお勧めします。 コードの移植方法の詳細については、「[C\+\+\/CLI 移行ガイド](../../dotnet/cpp-cli-migration-primer.md)」を参照してください。  
  
#### このコンパイラ オプションを Visual Studio で使用するには  
  
1.  **ソリューション エクスプローラー**でプロジェクト名を右クリックし、**\[プロパティ\]** をクリックして、プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  
  
2.  **\[構成プロパティ\]** フォルダーを選択します。  
  
3.  **\[全般\]** プロパティ ページで、**\[共通言語ランタイム サポート\]** プロパティを変更します。  
  
    > [!NOTE]
    >  **\/clr** が **\[プロパティ ページ\]** ダイアログ ボックスで有効になっている場合は、**\/clr** と互換性のないコンパイラ オプション プロパティも必要に応じて調整されます。 たとえば、**\/RTC** が設定された後で **\/clr** が有効になった場合、**\/RTC** はオフになります。  
    >   
    >  また、**\/clr** アプリケーションをデバッグする場合、**\[デバッガーの種類\]** プロパティを **\[混合\]** または **\[マネージのみ\]** に設定します。 詳細については、「[C\+\+ デバッグ構成のプロジェクト設定](../Topic/Project%20Settings%20for%20a%20C++%20Debug%20Configuration.md)」を参照してください。  
  
     モジュールの作成方法の詳細については、「[\/NOASSEMBLY \(MSIL モジュールの作成\)](../../build/reference/noassembly-create-a-msil-module.md)」を参照してください。  
  
#### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAsManaged%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)