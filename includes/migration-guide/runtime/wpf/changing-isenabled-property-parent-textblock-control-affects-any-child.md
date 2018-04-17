### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a><span data-ttu-id="e01ab-101">子コントロールに影響を与える、TextBlock コントロールの親の IsEnabled プロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="e01ab-101">Changing the IsEnabled property of the parent of a TextBlock control affects any child controls</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e01ab-102">説明</span><span class="sxs-lookup"><span data-stu-id="e01ab-102">Details</span></span>|<span data-ttu-id="e01ab-103">.NET Framework 4.6.2、変更以降の<xref:System.Windows.UIElement.IsEnabled?displayProperty=name>の親のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=name>コントロール (ハイパーリンクやボタンなど) などの子コントロールに影響を与える、<xref:System.Windows.Controls.TextBlock?displayProperty=name>コントロール。 .NET Framework 4.6.1 以前のバージョンで、内部コントロール、<xref:System.Windows.Controls.TextBlock?displayProperty=name>の状態を常に反映されませんでした、<xref:System.Windows.UIElement.IsEnabled?displayProperty=name>のプロパティ、<xref:System.Windows.Controls.TextBlock?displayProperty=name>親。</span><span class="sxs-lookup"><span data-stu-id="e01ab-103">Starting with the .NET Framework 4.6.2, changing the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the parent of a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control affects any child controls (such as hyperlinks and buttons) of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.In the .NET Framework 4.6.1 and earlier versions, controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> did not always reflect the state of the <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> property of the <xref:System.Windows.Controls.TextBlock?displayProperty=name> parent.</span></span>|
|<span data-ttu-id="e01ab-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="e01ab-104">Suggestion</span></span>|<span data-ttu-id="e01ab-105">なし。</span><span class="sxs-lookup"><span data-stu-id="e01ab-105">None.</span></span> <span data-ttu-id="e01ab-106">この変更は、<xref:System.Windows.Controls.TextBlock?displayProperty=name> コントロール内部のコントロールに期待される動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="e01ab-106">This change conforms to the expected behavior for controls inside a <xref:System.Windows.Controls.TextBlock?displayProperty=name> control.</span></span>|
|<span data-ttu-id="e01ab-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="e01ab-107">Scope</span></span>|<span data-ttu-id="e01ab-108">マイナー</span><span class="sxs-lookup"><span data-stu-id="e01ab-108">Minor</span></span>|
|<span data-ttu-id="e01ab-109">Version</span><span class="sxs-lookup"><span data-stu-id="e01ab-109">Version</span></span>|<span data-ttu-id="e01ab-110">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e01ab-110">4.6.2</span></span>|
|<span data-ttu-id="e01ab-111">型</span><span class="sxs-lookup"><span data-stu-id="e01ab-111">Type</span></span>|<span data-ttu-id="e01ab-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="e01ab-112">Runtime</span></span>|
|<span data-ttu-id="e01ab-113">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e01ab-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
