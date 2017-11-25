<!DOCTYPE html>
<html>
	<body>
		<article class="markdown-body entry-content">
			<h1>Shopine REST Service API</h1>
			<p>
				<h2>Table of contents</h2>
			</p>
			<ul>
				<li>
					<a href="#user-content-summary">Summary</a>
				</li>
				<li>
					<a href="#user-content-input">Input Parameters</a>
				</li>
				<li>
					<a href="#user-content-output">Output</a>
				</li>
				<li>
					<a href="#user-content-samples">Sample Clients</a>
				</li>
				<li>
					<a href="#user-content-serviceurl">Shopine Service URL</a>
				</li>
				<li>
					<a href="#user-content-qna">Questions and comments</a>
				</li>
			</ul>
						<h2>
				<a id="user-content-summary" class="anchor"  aria-hidden="true" />Summary</h2>
			<p>
				<a name="user-content-summary" /> Shopine REST API enables one stop search of products from some of the most popular on-line retailers, such as Amazon and ebay. One single search action from client will trigger the service to spin off multiple searches across the retailers. The searches across multiple retailers happen con-currently. No long wait. The service aggregates returns from all retailers in a single return in a unified format to client. The service can be easily consumed by variety of clients, such as desktop, mobile, and web apps.</p>
			<p>
				<a name="user-content-summary" />Following sections describe details on how to invoke this service.</p>
			<h2>
				<a id="user-content-input" class="anchor"  aria-hidden="true" />Input Parameters</h2>
			<p>
					<table border="1">
						<tbody>
							<tr>
								<th>Parameter</th>
								<th>Description</th>
								<th>Required</th>
							</tr>
							<tr>
								<td>
									<code class="code">kw</code>
								</td>
								<td>
									<p>Keywords. Multiple keywords can be entered separated by space. To have highly relevant search result, use keywords specific to the products being searched. 
                                    </p>
									<p>Type: String</p>
									<p>Default: None</p>
								</td>
								<td>Yes</td>
							</tr>
							<tr>
								<td>
									<code class="code">loc</code>
								</td>
								<td>
									<p>Limit search to items located in certain countries only. Supported countries: Canada, U.S., U.K.
                                    </p>
									<p>Type: String. Valid values: CA, US, GB, ANY</p>
									<p>Default: ANY</p>
								</td>
								<td>No</td>
							</tr>
							<tr>
								<td>
									<code class="code">minp</code>
								</td>
								<td>
									<p>Min price of search products. It can be used to have more relevant search results.
                                    </p>
									<p>Type: Number</p>
									<p>Default: None</p>
								</td>
								<td>No</td>
							</tr>
							<tr>
								<td>
									<code class="code">maxp</code>
								</td>
								<td>
									<p>Max price of search products. It can be used to have more relevant search results.
                                    </p>
									<p>Type: Number</p>
									<p>Default: None</p>
								</td>
								<td>No</td>
							</tr>
							<tr>
								<td>
									<code class="code">returnFormat</code>
								</td>
								<td>
									<p>Specify return result format. Valid values: XML, JSON	
                                    </p>
									<p>Type: String</p>
									<p>Default: JSON</p>
								</td>
								<td>No</td>
							</tr>
						</tbody>
					</table>
		</p>	
			<h2>
				<a id="user-content-output" class="anchor" aria-hidden="true"/>Output</h2>
			<p>
				<a name="user-content-output" />Output contains status section and ItemList if operation successful. Each item in ItemList contains following major data elements.
				<br></br>
				<table border="1">
                              <tbody>
							  <tr>
                                 <th>Name</th>
                                 <th>Description</th>
                              </tr>
                              <tr>
                                 <td>
                                    <code class="code">ItemName</code>
                                 </td>
                                 <td>
                                 Full name of the product.
                                 </td>
                              </tr>
                              <tr>
                                 <td>
                                    <code class="code">ItemThumbImageURL</code>
                                 </td>
                                 <td>
                                 Thumb image url of the product.
                                 </td>
                              </tr>
                              <tr>
                                 <td>
                                    <code class="code">ItemURL</code>
                                 </td>
                                 <td>
                                 URL of the product.
                                 </td>
                              </tr>
                              <tr>
                                 <td>
                                    <code class="code">ItemPrice.PriceString</code>
                                 </td>
                                 <td>
                                 Formatted price (including. currency code) of the product.
                                 </td>
                              </tr>
                              <tr>
                                 <td>
                                    <code class="code">ItemSource</code>
                                 </td>
                                 <td>
                                 Source website of the product, e.g. Amazon, ebay, and etc.
                                 </td>
                              </tr>
                           </tbody>
				</table>
				<p>
				<a name="user-content-output" />Here's a sample request: <br/><br/>
				<a name="user-content-output" /><code class="code">http://datacaremaster.com/itemsapi/api/items/?kw=northface+ski+jacket+womens+xl&maxp=90&loc=gb&returnFormat=xml</code>
				<br/><br/>
				<a name="user-content-output" />To see the corresponding output, click <a href="./ShopineServiceSampleReturn.xml">here.</a> 
				<br/><br/>
				<a name="user-content-output" />The schema governing output data structure can be found <a href="./ItemInfoDataModel.xsd">here.</a>
				</p>
			</p>
				<h2><a id="user-content-samples" class="anchor" aria-hidden="true"/>Shopine Client Samples</h2> 
			<p>
			<a name="user-content-samples" />We've built a few clients to consume Shopine Service. Following client samples are available from <a href="">here.</a>
			</p>
			<ul>
				<li>
					Desktop app
			   </li>
				<li>
					Web app
			   </li>
				<li>
					Mobile app
			   </li>
			</ul>
			<h2>
				<a id="user-content-serviceurl" class="anchor" aria-hidden="true" />Shopine Service URL</h2>
			<p>
			<a name="user-content-serviceurl" />Shopine Service URL: <code class="code">http://datacaremaster.com/itemsapi/api/items/</code>
			</p>
			<h2>
				<a id="user-content-qna" class="anchor" aria-hidden="true" />Questions and comments</h2>
			<p>
				<a name="user-content-qna" />if you have any questions or comments, please <a href="http://datacaremaster.com">contact us.</a>
			</p>
			<hr/>
Copyright (c) 2017 Datacaremaster.com. All rights reserved.
		</article>
	</body>
</html>
