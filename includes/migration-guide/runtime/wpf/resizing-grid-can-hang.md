### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="acbf8-101">ハングする可能性がグリッドのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="acbf8-101">Resizing a Grid can hang</span></span>

|   |   |
|---|---|
|<span data-ttu-id="acbf8-102">説明</span><span class="sxs-lookup"><span data-stu-id="acbf8-102">Details</span></span>|<span data-ttu-id="acbf8-103">無限ループがレイアウトの中に発生することができます、<code>T:System.Windows.Controls.Grid</code>次の状況で。</span><span class="sxs-lookup"><span data-stu-id="acbf8-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="acbf8-104">行の定義には、2 つが含まれている \*-行は、MinHeight と、MaxHeight 両方の宣言します。</span><span class="sxs-lookup"><span data-stu-id="acbf8-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="acbf8-105">コンテンツ、\*、行が対応する MaxHeight を超えていません。</span><span class="sxs-lookup"><span data-stu-id="acbf8-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="acbf8-106">最初の MinHeight グリッドの使用可能な高さを超えた (およびその他の固定または行の自動)</span><span class="sxs-lookup"><span data-stu-id="acbf8-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="acbf8-107">アプリの対象 .Net 4.7、または 4.7 割り当てアルゴリズムに設定してオプトインを指定 <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span><span class="sxs-lookup"><span data-stu-id="acbf8-107">The app targets .Net 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="acbf8-108">3 つ以上の行または列の場合は似ています、ループも発生します。 .Net 4.7.1 で問題が解決します。</span><span class="sxs-lookup"><span data-stu-id="acbf8-108">The loop would also happen with more than two rows, or in the analogous case for columns.The issue is fixed in .Net 4.7.1.</span></span>|
|<span data-ttu-id="acbf8-109">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="acbf8-109">Suggestion</span></span>|<span data-ttu-id="acbf8-110">.Net 4.7.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="acbf8-110">Upgrade to .Net 4.7.1.</span></span>  <span data-ttu-id="acbf8-111">また、4.7 割り当てアルゴリズムを必要としない場合は、次の構成設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="acbf8-111">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="acbf8-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="acbf8-112">Scope</span></span>|<span data-ttu-id="acbf8-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="acbf8-113">Edge</span></span>|
|<span data-ttu-id="acbf8-114">Version</span><span class="sxs-lookup"><span data-stu-id="acbf8-114">Version</span></span>|<span data-ttu-id="acbf8-115">4.7</span><span class="sxs-lookup"><span data-stu-id="acbf8-115">4.7</span></span>|
|<span data-ttu-id="acbf8-116">型</span><span class="sxs-lookup"><span data-stu-id="acbf8-116">Type</span></span>|<span data-ttu-id="acbf8-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="acbf8-117">Runtime</span></span>|
