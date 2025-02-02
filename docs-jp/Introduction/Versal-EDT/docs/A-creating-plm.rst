..
   Copyright 2000-2021 Xilinx, Inc.

   Apache ライセンス、バージョン 2.0 (以下「ライセンス」) に基づいてライセンス付与されています。
   「ライセンス」に準拠しないと、このファイルを使用することはできません。
   ライセンスのコピーは、次から入手できます。

       http://www.apache.org/licenses/LICENSE-2.0

   適切な法律で要求されるか、書面で同意された場合を除き、
   本ライセンスに基づいて配布されるソフトウェアは、明示的または黙示的を問わず、
   いかなる種類の保証または条件もなく、「現状のまま」配布されます。
   ライセンスに基づく権限とする特定の言語については、
   ライセンスを参照してください。


**************************
付録: PLM の作成
**************************

次に、Vitis |trade| ソフトウェア プラットフォームでプラットフォーム ローダーおよびマネージャー (PLM) の ELF ファイルを作成する手順を示します。Versal |trade| デバイスでは、PLM は PMC で実行され、APU および RPU のブートストラップに使用されます。

1.**[File]** → **[New]** → **[Application Project]** をクリックします。New Application Project ウィザードが開きます。

2.ウィザードの各ページで次の表の情報にづいて設定を選択します。

   **表 10: システム プロパティ設定**

   +-----------------+-----------------------+---------------------------+
   | Wizard Screen   | System Properties     | Setting or Command to Use |
   +=================+=======================+===========================+
   | Platform        | Create a new platform | Click the **Browse**      |
   |                 | from hardware (XSA)   | button to add your XSA    |
   |                 |                       | file.                     |
   +-----------------+-----------------------+---------------------------+
   |                 | Platform name         | plm_platform              |
   +-----------------+-----------------------+---------------------------+
   | Application     | Application project   | plm                       |
   | Project Details | name                  |                           |
   +-----------------+-----------------------+---------------------------+
   |                 | Select a system       | +Create New               |
   |                 | project               |                           |
   +-----------------+-----------------------+---------------------------+
   |                 | System project name   | plm_system                |
   +-----------------+-----------------------+---------------------------+
   |                 | Target processor      | psv_pmc_0                 |
   +-----------------+-----------------------+---------------------------+
   | Domain          | Select a domain       | +Create New               |
   +-----------------+-----------------------+---------------------------+
   |                 | Name                  | The default name assigned |
   +-----------------+-----------------------+---------------------------+
   |                 | Display Name          | The default name assigned |
   +-----------------+-----------------------+---------------------------+
   |                 | Operating System      | standalone                |
   +-----------------+-----------------------+---------------------------+
   |                 | Processor             | psv_pmc_0                 |
   |                 |                       |                           |
   |                 |                       | .. note::                 |
   |                 |                       |   If the psv_pmc_0 option | 
   |                 |                       |   is not visible under the|
   |                 |                       |   list of processors,     |
   |                 |                       |   check the box next to   |
   |                 |                       |   Show All processors in  |
   |                 |                       |   the hardware            |
   |                 |                       |   specification option to |
   |                 |                       |   view all the available  |
   |                 |                       |   target processors for   |
   |                 |                       |   the application project.|
   +-----------------+-----------------------+---------------------------+
   |                 | Architecture          | 32-bit                    |
   +-----------------+-----------------------+---------------------------+
   | Templates       | Available Templates   | Versal PLM                |
   +-----------------+-----------------------+---------------------------+

Vitis ソフトウェア プラットフォームは、[Explorer] ビューの下に PLM アプリケーション プロジェクトと edt_versal_wrapper プラットフォームを作成します。プラットフォーム プロジェクトを右クリックし、**[Build Project]** をクリックします。プラットフォーム プロジェクトをビルドしたら、plm_system プロジェクトを右クリックし、**[Build Project]** をクリックします。これにより、アプリケーション プロジェクトの Debug フォルダー内に `plm.elf` ファイルが生成されます。プロジェクトをビルドしたら、プラットフォームもビルドします。

-----------------------------------------------

この資料は 2021 年 8 月 12 日時点の表記バージョンの英語版を翻訳したもので、内容に相違が生じる場合には原文を優先します。資料によっては英語版の更新に対応していないものがあります。日本語版は参考用としてご使用の上、最新情報につきましては、必ず最新英語版をご参照ください。


.. |trade|  unicode:: U+02122 .. TRADEMARK SIGN
   :ltrim:
.. |reg|    unicode:: U+000AE .. REGISTERED TRADEMARK SIGN
   :ltrim:


