### <a name="icontobitmap-successfully-converts-icons-with-png-frames-into-bitmap-objects"></a><span data-ttu-id="a1d1c-101">Icon.ToBitmap がビットマップ オブジェクトに PNG フレームを含んだアイコンを正常に変換します。</span><span class="sxs-lookup"><span data-stu-id="a1d1c-101">Icon.ToBitmap successfully converts icons with PNG frames into Bitmap objects</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a1d1c-102">説明</span><span class="sxs-lookup"><span data-stu-id="a1d1c-102">Details</span></span>|<span data-ttu-id="a1d1c-103">以降、.NET Framework 4.6 を対象とするアプリで、<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>メソッドがビットマップ オブジェクトに PNG フレームを含んだアイコンを正常に変換します。 .NET Framework 4.5.2 および以前のバージョンを対象とするアプリで、<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType>メソッドがスローされます、<xref:System.ArgumentOutOfRangeException>アイコン オブジェクトに PNG フレームがある場合は例外です。この変更はアプリを .NET Framework 4.6 を対象として再コンパイルして、特別な処理を実装している、<xref:System.ArgumentOutOfRangeException>アイコン オブジェクトに PNG フレームがある場合にスローされます。</span><span class="sxs-lookup"><span data-stu-id="a1d1c-103">Starting with the apps that target the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into Bitmap objects.In apps that target the .NET Framework 4.5.2 and earlier versions, the  <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the Icon object has PNG frames.This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an Icon object has PNG frames.</span></span> <span data-ttu-id="a1d1c-104">.NET Framework 4.6 で実行している場合は、正常に変換が行われ、 <xref:System.ArgumentOutOfRangeException> がスローされることはないため、例外ハンドラーは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="a1d1c-104">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>|
|<span data-ttu-id="a1d1c-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a1d1c-105">Suggestion</span></span>|<span data-ttu-id="a1d1c-106">この動作が望ましくない場合は、次の要素を追加することによって、以前の動作を保持できます、 <code>&lt;runtime&gt;</code> app.config ファイルのセクション。</span><span class="sxs-lookup"><span data-stu-id="a1d1c-106">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="language-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true&quot; /&gt;&#13;&#10;</code></pre><span data-ttu-id="a1d1c-107">App.config ファイルが既に含まれている場合、<code>AppContextSwitchOverrides</code>要素を新しい値は、次のように value 属性とマージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1d1c-107">If the app.config file already contains the <code>AppContextSwitchOverrides</code> element, the new value should be merged with the value attribute like this:</span></span><pre><code class="language-xml">&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Drawing.DontSupportPngFramesInIcons=true;&lt;previous key&gt;=&lt;previous value&gt;&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="a1d1c-108">スコープ</span><span class="sxs-lookup"><span data-stu-id="a1d1c-108">Scope</span></span>|<span data-ttu-id="a1d1c-109">マイナー</span><span class="sxs-lookup"><span data-stu-id="a1d1c-109">Minor</span></span>|
|<span data-ttu-id="a1d1c-110">Version</span><span class="sxs-lookup"><span data-stu-id="a1d1c-110">Version</span></span>|<span data-ttu-id="a1d1c-111">4.6</span><span class="sxs-lookup"><span data-stu-id="a1d1c-111">4.6</span></span>|
|<span data-ttu-id="a1d1c-112">型</span><span class="sxs-lookup"><span data-stu-id="a1d1c-112">Type</span></span>|<span data-ttu-id="a1d1c-113">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="a1d1c-113">Retargeting</span></span>|
|<span data-ttu-id="a1d1c-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a1d1c-114">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Icon.ToBitmap?displayProperty=nameWithType></li></ul>|
