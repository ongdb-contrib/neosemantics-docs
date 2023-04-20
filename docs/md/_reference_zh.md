## Neosemantics 参考指南

Neosemantics 中所有可用存储过程、函数和扩展的完整列表。(Convert MD: https://pandoc.org/try/)

### 存储过程

#### RDF 导入

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">存储过程名称</th>
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">说明和示例用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.importRDF</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>从URL（文件或http）获取RDF，并将其作为属性图存储在ONgDB中。此过程需要索引
:Resource(uri)</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.importRDFSnippet</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>包含有效 RDF 片段的字符串</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>导入作为参数传递的 RDF
代码段，并将其作为属性图存储在 ONgDB 中。 此过程需要索引
:Resource(uri)</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.importQuadRDF</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: TriG,N-Quads)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>导入 RDF
Quads。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.importOntology</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（本体导入）中的参数</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>导入类、属性（数据类型和对象）、其层次结构以及域和范围信息。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.streamRDF</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>解析 RDF
并将每个三元组流式传输为具有 &lt;S，P，O&gt;
的记录，以及文本值的数据类型和语言标记。不写入数据库。当您想要以自定义方式将
RDF 数据集的 ONgDB 图片段导入到 ONgDB 图形片段中时，此 SP
非常有用。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.streamRDFSnippet</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>包含有效 RDF 片段的字符串</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>解析作为文本传递的 RDF
代码段，并将每个三元组流式传输为具有 &lt;S，P，O&gt;
的记录，以及文本值的数据类型和语言标记。不写入数据库。另请参阅
<code>streamRDF</code>。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.previewRDF</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>解析 RDF
并生成虚拟节点和关系，以便在 ONgDB
浏览器中预览。不写入数据库。请注意，这对于 SMALL
数据集的初步可视化分析已足够。考虑你想在浏览器中呈现多少个节点。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.previewRDFSnippet</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>包含有效 RDF 片段的字符串</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>解析作为参数传递的 RDF
片段（不从 url 检索），并生成虚拟节点和关系，以便在 ONgDB
浏览器中预览。不写入数据库。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.deleteRDF</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>从 ONgDB
中删除三元组。在图上工作的结果是通过semantics.importRDF（）导入RDF。删除配置必须与导入时使用的配置匹配。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.deleteRDFSnippet</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>包含有效 RDF 片段的字符串</p></li>
<li><p>序列化格式 (有效格式: Turtle, N-Triples, JSON-LD, TriG,
RDF/XML)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>从 ONgDB
中删除作为第一个参数传递的三元组。以相同的方式工作，并采用与
<code>deleteRDF</code> 相同的参数。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.deleteQuadRDF</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>数据集的 URL</p></li>
<li><p>序列化格式 (有效格式: TriG,N-Quads)</p></li>
<li><p>可选的 Map 参数，使用下表（RDF 导入参数）中的参数</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>从 ONgDB 中删除
Quads。在通过semantics.importQuadRDF（）导入RDF四边形的结果图上工作。删除配置必须与导入时使用的配置匹配。</p></td>
</tr>
</tbody>
</table>

##### RDF 导入参数

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">值(默认值)</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>handleVocabUris</p></td>
<td
class="tableblock halign-left valign-top"><p>'SHORTEN','IGNORE','MAP','KEEP'
('SHORTEN')</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p><code>SHORTEN</code>,
使用属性名称、关系名称和标签的前缀缩短完整的 URI。</p></li>
<li><p><code>IGNORE</code> URI 将被忽略，仅保留本地名称。</p></li>
<li><p><code>MAP</code> 导入时应用词汇元素映射。</p></li>
<li><p><code>KEEP</code> uris保持不变。</p></li>
</ul>
</div>
</div></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>applyNeo4jNaming</p></td>
<td class="tableblock halign-left valign-top"><p>boolean
(false)</p></td>
<td class="tableblock halign-left valign-top"><p>设置为 true 并与
<code>handleVocabUris: IGNORE</code> 使用, ONgDB
大写应用于词汇元素（关系类型的大写字母，标签的大写优先等）</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>handleMultival</p></td>
<td class="tableblock halign-left valign-top"><p>'OVERWRITE', 'ARRAY'
('OVERWRITE')</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p><code>OVERWRITE</code>
属性值保持单值。导入的RDF中的多个值被覆盖（仅保留最后一个值）</p></li>
<li><p><code>ARRAY</code>
属性存储在一个数组中，可以存储多个值。所有这些，除非设置了
<code>multivalPropList</code>。</p></li>
</ul>
</div>
</div></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>multivalPropList</p></td>
<td class="tableblock halign-left valign-top"><p>list of strings
([])</p></td>
<td
class="tableblock halign-left valign-top"><p>要存储为数组的属性名称（完整
uri）列表。其余的被视为 <code>OVERWRITE</code>。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>keepLangTag</p></td>
<td class="tableblock halign-left valign-top"><p>boolean
(false)</p></td>
<td class="tableblock halign-left valign-top"><p>设置为 true
时，语言标记将与属性值一起保留。适用于多语言数据集。 使用帮助程序函数
<code>getLangValue</code> 获取特定值。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>predicateExclusionList</p></td>
<td class="tableblock halign-left valign-top"><p>list of strings
([])</p></td>
<td class="tableblock halign-left valign-top"><p>解析 RDF
时要忽略且不存储在 ONgDB 中的谓词（完整 uri）列表。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>typesToLabels</p></td>
<td class="tableblock halign-left valign-top"><p>boolean (true)</p></td>
<td class="tableblock halign-left valign-top"><p>设置为 true
时，RDF：type 语句将作为节点标签导入 ONgDB 中。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>languageFilter</p></td>
<td
class="tableblock halign-left valign-top"><p>['en','fr','es',…​]</p></td>
<td
class="tableblock halign-left valign-top"><p>设置后，仅导入具有此语言标记的文本属性（或未标记的属性）。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>headerParams</p></td>
<td class="tableblock halign-left valign-top"><p>map {}</p></td>
<td class="tableblock halign-left valign-top"><p>要在 HTTP GET
请求中传递的参数，如果是 POST 请求，则为 <code>payload</code>。
&lt;br&gt; 示例:
<code>{ authorization: 'Basic user:pwd', Accept: 'application/rdf+xml'}</code></p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>commitSize</p></td>
<td class="tableblock halign-left valign-top"><p>integer
(25000)</p></td>
<td class="tableblock halign-left valign-top"><p>每 N
个三元组提交一次事务。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>nodeCacheSize</p></td>
<td class="tableblock halign-left valign-top"><p>integer
(10000)</p></td>
<td class="tableblock halign-left valign-top"><p>将 N
个节点保留在缓存中以最大程度地减少从数据库读取的数据。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>verifyUriSyntax</p></td>
<td class="tableblock halign-left valign-top"><p>boolean (true)</p></td>
<td class="tableblock halign-left valign-top"><p>默认情况下，将检查 URI
语法。可以通过将此参数设置为 <code>false</code> 来禁用。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>keepCustomDataTypes</p></td>
<td class="tableblock halign-left valign-top"><p>boolean(false)</p></td>
<td class="tableblock halign-left valign-top"><p>设置为 true
时，包含自定义数据类型的所有属性都将另存为字符串，后跟其自定义数据类型IRIs。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>customDataTypedPropList</p></td>
<td class="tableblock halign-left valign-top"><p>list of strings
([])</p></td>
<td
class="tableblock halign-left valign-top"><p>设置后，仅导入此列表中文本属性的自定义数据类型。</p></td>
</tr>
</tbody>
</table>

##### 本体导入参数

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">值(默认值)</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>predicateExclusionList</p></td>
<td class="tableblock halign-left valign-top"><p>list of strings
([])</p></td>
<td class="tableblock halign-left valign-top"><p>解析 RDF
时要忽略且不存储在 ONgDB 中的谓词（完整 uri）列表。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>headerParams</p></td>
<td class="tableblock halign-left valign-top"><p>map {}</p></td>
<td class="tableblock halign-left valign-top"><p>要在 HTTP GET
请求中传递的参数，如果是 POST 请求，则为 <code>payload</code>。
&lt;br&gt; 示例:
<code>{ authorization: 'Basic user:pwd', Accept: 'application/rdf+xml'}</code></p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>commitSize</p></td>
<td class="tableblock halign-left valign-top"><p>integer
(25000)</p></td>
<td class="tableblock halign-left valign-top"><p>每 N
个三元组提交一次事务。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>nodeCacheSize</p></td>
<td class="tableblock halign-left valign-top"><p>integer
(10000)</p></td>
<td class="tableblock halign-left valign-top"><p>将 N
个节点保留在缓存中以最大程度地减少从数据库读取的数据。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>verifyUriSyntax</p></td>
<td class="tableblock halign-left valign-top"><p>boolean (true)</p></td>
<td class="tableblock halign-left valign-top"><p>默认情况下，将检查 URI
语法。可以通过将此参数设置为 <code>false</code> 来禁用。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>classLabelName</p></td>
<td class="tableblock halign-left valign-top"><p>string
('Class')</p></td>
<td
class="tableblock halign-left valign-top"><p>本体中类的标签。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>subClassOfRelName</p></td>
<td class="tableblock halign-left valign-top"><p>string ('SCO')</p></td>
<td
class="tableblock halign-left valign-top"><p><code>rdfs：subClassOf</code>
语句的关系名称。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>dataTypePropertyLabelName</p></td>
<td class="tableblock halign-left valign-top"><p>string
('Property')</p></td>
<td
class="tableblock halign-left valign-top"><p>数据类型属性定义（属性）的标签。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>objectPropertyLabelName</p></td>
<td class="tableblock halign-left valign-top"><p>string
('Relationship')</p></td>
<td
class="tableblock halign-left valign-top"><p>对象属性定义（关系）的标签。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>subPropertyOfRelName</p></td>
<td class="tableblock halign-left valign-top"><p>string ('SPO')</p></td>
<td
class="tableblock halign-left valign-top"><p><code>rdfs：subPropertyOf</code>
语句的关系。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>domainRelName</p></td>
<td class="tableblock halign-left valign-top"><p>string
('DOMAIN')</p></td>
<td
class="tableblock halign-left valign-top"><p>类和数据类型属性/对象属性之间的域关系。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>rangeRelName</p></td>
<td class="tableblock halign-left valign-top"><p>string
('RANGE')</p></td>
<td
class="tableblock halign-left valign-top"><p>类和数据类型属性/对象属性之间的范围关系。</p></td>
</tr>
</tbody>
</table>

#### RDF 导入实用工具

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">存储过程</th>
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">说明和示例用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.addNamespacePrefix</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>prefix: 字符串 (例如 <code>owl</code>)</p></li>
<li><p>namespace: URI 的命名空间部分 (例如 <a
href="http://www.w3.org/2002/07/owl#"
class="bare"><code>http://www.w3.org/2002/07/owl#</code></a>)</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>添加命名空间 -
前缀对定义，用于RDF导入/导出。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.listNamespacePrefixes</p></td>
<td class="tableblock halign-left valign-top"><p>-</p></td>
<td
class="tableblock halign-left valign-top"><p>列出所有当前定义的命名空间前缀定义。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.addNamespacePrefixesFromText</p></td>
<td class="tableblock halign-left valign-top"><p>String</p></td>
<td class="tableblock halign-left valign-top"><p>[实验]
从文本中提取命名空间前缀定义
作为输入（SPARQL，RDF/XML，Turtle）传递并添加每个命名空间前缀对，以便它可以用于RDF导入/导出。</p></td>
</tr>
</tbody>
</table>

#### 模型映射

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">存储过程名称</th>
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">说明和示例用法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.addSchema</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>schema/vocabulary/ontology 的 URL</p></li>
<li><p>序列化中使用的前缀</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>创建对词汇表的引用。需要定义映射。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.dropSchema</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>schema/vocabulary/ontology 的 URL</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>删除词汇引用和所有关联的映射。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.listSchemas</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>optional filter string</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>返回所有词汇引用。设置筛选器字符串时，仅返回在其
uri 或关联前缀中包含搜索字符串的schema。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.addCommonSchemas</p></td>
<td class="tableblock halign-left valign-top"><p>no prams</p></td>
<td
class="tableblock halign-left valign-top"><p>创建对许多流行词汇表的引用，包括
schema.org, Dublin Core, SKOS, OWL, etc</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.addMappingToSchema</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>schema/voc/ontology 的 URL</p></li>
<li><p>ONgDB 图中元素的名称（属性名称、标签或关系类型）</p></li>
<li><p>公共架构中的匹配元素（类、数据类型属性或对象属性）。仅元素的本地名称</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>为 ONgDB 数据库 schema
中的元素创建到词汇元素的映射。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.dropMapping</p></td>
<td class="tableblock halign-left valign-top"><p>*
映射的数据库元素名称以删除映射</p></td>
<td
class="tableblock halign-left valign-top"><p>返回指示删除成功/失败的输出文本消息。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.mapping.listMappings</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>optional filter string</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>返回包含所有当前定义的映射的列表。无论传递筛选器字符串，仅传递包含字符串的映射
返回数据库元素名称或schema元素 URI。</p></td>
</tr>
</tbody>
</table>

#### 推理

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">存储过程名称</th>
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.inference.nodesLabelled</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>标签名称</p></li>
<li><p>参数如下表（推理参数）所述</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>返回带有指定标签的节点或其子标签的所有节点。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.inference.nodesInCategory</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>表示类别节点。</p></li>
<li><p>参数如下表（推理参数）所述</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>返回指定类别的节点或其子类别的所有节点。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.inference.getRels</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>开始节点</p></li>
<li><p>(实际 或 '虚拟') 关系类型</p></li>
<li><p>参数如下表（推理参数）所述</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>返回类型为
<code>virtRel</code> 或其子类型的所有关系以及目标节点。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.inference.hasLabel
<strong>(函数)</strong></p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>节点</p></li>
<li><p>标签名</p></li>
<li><p>参数如下表（推理参数）所述</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>检查节点是否被显式或隐式标记为指定“标签”。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.inference.inCategory
<strong>(函数)</strong></p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>表示实例的节点</p></li>
<li><p>表示节点类别</p></li>
<li><p>参数如下表（推理参数）所述</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>检查节点是显式还是隐式在类别中。</p></td>
</tr>
</tbody>
</table>

##### 推理参数

###### 参数说明：过程 semantics.inference.nodesLabelled 和 函数 semantics.inference.hasLabel

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">值(默认值)</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>catLabel</p></td>
<td class="tableblock halign-left valign-top"><p>String
('Label')</p></td>
<td
class="tableblock halign-left valign-top"><p>用于描述类别的节点的标签。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>catNameProp</p></td>
<td class="tableblock halign-left valign-top"><p>String
('name')</p></td>
<td
class="tableblock halign-left valign-top"><p>包含类别名称的属性名称。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>subCatRel</p></td>
<td class="tableblock halign-left valign-top"><p>String ('SLO')</p></td>
<td
class="tableblock halign-left valign-top"><p>将子类别连接到其父类别的关系类型。</p></td>
</tr>
</tbody>
</table>

###### 参数说明：过程 semantics.inference.nodesInCategory 和 函数 semantics.inference.inCategory

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">值(默认值)</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>inCatRel</p></td>
<td class="tableblock halign-left valign-top"><p>String
('IN_CAT')</p></td>
<td
class="tableblock halign-left valign-top"><p>将实例节点连接到类别节点的关系类型。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>subCatRel</p></td>
<td class="tableblock halign-left valign-top"><p>String ('SCO')</p></td>
<td
class="tableblock halign-left valign-top"><p>将子类别连接到其父类别的关系类型。</p></td>
</tr>
</tbody>
</table>

###### 参数说明：过程 semantics.inference.getRels

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">值(默认值)</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>relLabel</p></td>
<td class="tableblock halign-left valign-top"><p>String
('Relationship')</p></td>
<td
class="tableblock halign-left valign-top"><p>用于描述关系的节点的标签。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>relNameProp</p></td>
<td class="tableblock halign-left valign-top"><p>String
('name')</p></td>
<td
class="tableblock halign-left valign-top"><p>包含关系名称的属性名称。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>subRelRel</p></td>
<td class="tableblock halign-left valign-top"><p>String ('SRO')</p></td>
<td
class="tableblock halign-left valign-top"><p>将子关系与其父关系连接起来的关系类型。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>relDir</p></td>
<td class="tableblock halign-left valign-top"><p>'&lt;','&gt;'
('')</p></td>
<td class="tableblock halign-left valign-top"><p>关系的方向。 '&gt;'
对于传出关系，'&lt;' 对于传入关系，默认（空）表示双向.</p></td>
</tr>
</tbody>
</table>

### 实用功能函数

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">函数名称</th>
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.getIRILocalName</p></td>
<td class="tableblock halign-left valign-top"><p>URI string</p></td>
<td class="tableblock halign-left valign-top"><p>返回 URI
的本地部分（去除命名空间）。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.getIRINamespace</p></td>
<td class="tableblock halign-left valign-top"><p>URI string</p></td>
<td class="tableblock halign-left valign-top"><p>返回 URI
的命名空间部分（去掉本地部分）。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.getDataType</p></td>
<td class="tableblock halign-left valign-top"><p>string (a property
value)</p></td>
<td class="tableblock halign-left valign-top"><p>返回属性值的
XMLSchema（或自定义）数据类型（如果存在）。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.getLangValue</p></td>
<td class="tableblock halign-left valign-top"><p>string (a property
value)</p></td>
<td
class="tableblock halign-left valign-top"><p>返回语言标记作为第一个参数传递的值，如果没有提供的语言标记的值，则返回
null。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.getLangTag</p></td>
<td class="tableblock halign-left valign-top"><p>string (a property
value)</p></td>
<td
class="tableblock halign-left valign-top"><p>返回与属性值关联的语言标记（如果存在），如果不存在语言标记，则返回
null。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.hasLangTag</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>String (lang-tag)</p></li>
<li><p>String (a property value)</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>如果值将语言标记作为第一个参数传递为
false，则返回 true。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.getValue</p></td>
<td class="tableblock halign-left valign-top"><p>string (a property
value)</p></td>
<td
class="tableblock halign-left valign-top"><p>在去除数据类型信息或语言标记（如果存在）后返回属性的数据类型的值。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.shortFromUri</p></td>
<td class="tableblock halign-left valign-top"><p>string (a URI)</p></td>
<td
class="tableblock halign-left valign-top"><p>返回使用现有命名空间定义的
IRI 的缩短版本。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>semantics.uriFromShort</p></td>
<td class="tableblock halign-left valign-top"><p>string (a shortened
URI)</p></td>
<td
class="tableblock halign-left valign-top"><p>返回扩展的（完整）URI，给定在加载过程中使用<strong>semantics.importRDF</strong>创建的缩短URI。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>semantics.importJSONAsTree</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>要将导入的 JSON 链接到的节点</p></li>
<li><p>JSON 片段</p></li>
<li><p>(optional) 关系名称，将 JSON
的根节点链接到作为第一个参数传递的节点</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>通过将 JSON
映射到节点和关系来导入 JSON (JSON-LD style). 需要唯一性约束
:Resource(uri)</p></td>
</tr>
</tbody>
</table>

### 扩展（HTTP 端点）

<table class="tableblock frame-all grid-all stretch">
<colgroup>
<col style="width: 15%" />
<col style="width: 5%" />
<col style="width: 45%" />
<col style="width: 35%" />
</colgroup>
<thead>
<tr class="header">
<th class="tableblock halign-left valign-top">接口</th>
<th class="tableblock halign-left valign-top">类型</th>
<th class="tableblock halign-left valign-top">参数</th>
<th class="tableblock halign-left valign-top">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>/rdf/describe/id/&lt;nodeid&gt;</p></td>
<td class="tableblock halign-left valign-top"><p>GET</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>nodeid: 包含节点 ID 的 path 参数</p></li>
<li><p>excludeContext:
可选命名参数。如果当前输出不包括连接的节点，则只需选择一个节点。</p></li>
<li><p>format: RDF 序列化格式。如果存在，它将覆盖标头参数
<strong>accept</strong>.</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>生成所选节点的 RDF
序列化。格式将由标头中的 <strong>accept</strong> 参数确定。默认值为
Turtle。</p></td>
</tr>
<tr class="even">
<td
class="tableblock halign-left valign-top"><p>/rdf/describe/uri/&lt;nodeuri&gt;</p></td>
<td class="tableblock halign-left valign-top"><p>GET</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>nodeuri: 包含节点的 （urlencoded） uri 的路径参数。</p></li>
<li><p>excludeContext:
（可选）如果当前输出不包括连接的节点，则只需选择一个。</p></li>
<li><p>graphuri:（可选）如果存在并且图形包含Quad信息，则仅返回所选命名图形中的语句。参数的值是命名图的（urlencoded）uri。</p></li>
<li><p>format: RDF 序列化格式。如果存在，它将覆盖标头参数
<strong>accept</strong>。</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>生成所选节点的 RDF
序列化。它适用于从RDF数据集导入的模型，通过
<strong>semantics.importRDF</strong>,
<strong>semantics.importQuadRDF</strong> 或者以节点标记为 ：Resource
并具有 URI 的方式构建。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>/rdf/describe/find/&lt;l&gt;/&lt;p&gt;/&lt;v&gt;</p></td>
<td class="tableblock halign-left valign-top"><p>GET</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>该方法采用作为 URL
中的路径参数传递的三个参数：/&lt;l&gt;&lt;p&gt;/&lt;v&gt;。它们分别表示标签、属性名称和属性值。</p></li>
<li><p>excludeContext:
可选命名参数。如果当前输出不包括连接的节点，则只需选择一个节点。</p></li>
<li><p>valType: 当属性值不被视为字符串时是必需的。有效值：INTEGER, FLOAT
and BOOLEAN</p></li>
<li><p>format: RDF 序列化格式。如果存在，它将覆盖标头参数
<strong>accept</strong>。</p></li>
</ul>
</div>
</div></td>
<td
class="tableblock halign-left valign-top"><p>返回与标签和属性值上的筛选器匹配的节点。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>/rdf/cypher</p></td>
<td class="tableblock halign-left valign-top"><p>POST</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="paragraph">
<p>POST request taking as parameter a JSON map with the following
keys:</p>
</div>
<div class="ulist">
<ul>
<li><p>cypher: 要运行的cypher查询</p></li>
<li><p>cypherParams: cypher查询的参数</p></li>
<li><p>showOnlyMapped: （可选，默认值为
false）如果当前输出将排除未映射的元素（请参阅如何定义标签、属性、关系的映射）</p></li>
<li><p>format: RDF 序列化格式。如果存在，它将覆盖标头参数
<strong>accept</strong>。</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>生成 Cypher
查询返回的节点和关系的 RDF 序列化。</p></td>
</tr>
<tr class="odd">
<td
class="tableblock halign-left valign-top"><p>/rdf/cypheronrdf</p></td>
<td class="tableblock halign-left valign-top"><p>POST</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="paragraph">
<p>与 <code>/rdf/cypher</code> 相同的参数</p>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>与
<code>/rdf/cypher</code>
相同，但它适用于通过<strong>semantics.importRDF</strong>从RDF数据集导入或内置的模型
节点标记为 ：Resource 并具有 URI 的方式。</p></td>
</tr>
<tr class="even">
<td class="tableblock halign-left valign-top"><p>/rdf/onto</p></td>
<td class="tableblock halign-left valign-top"><p>GET</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>format: RDF 序列化格式。如果存在，它将覆盖标头参数
<strong>accept</strong>。</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>返回基于图模式的 OWL
本体。</p></td>
</tr>
<tr class="odd">
<td class="tableblock halign-left valign-top"><p>/rdf/ontonrdf</p></td>
<td class="tableblock halign-left valign-top"><p>GET</p></td>
<td class="tableblock halign-left valign-top"><div class="content">
<div class="ulist">
<ul>
<li><p>format: RDF 序列化格式。如果存在，它将覆盖标头参数
<strong>accept</strong>。</p></li>
</ul>
</div>
</div></td>
<td class="tableblock halign-left valign-top"><p>与
<code>/rdf/onto</code> 相同，但它适用于通过
<strong>semantics.importRDF</strong> 从 RDF 数据集导入或内置的模型
节点标记为 ：Resource 并具有 URI 的方式。</p></td>
</tr>
</tbody>
</table>

Last updated 2023-04-19 14:41:29 +0800