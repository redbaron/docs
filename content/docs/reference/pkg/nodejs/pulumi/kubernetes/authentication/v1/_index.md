---
title: Module authentication/v1
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->

<a href="../../">@pulumi/kubernetes</a> &gt; <a href="../">authentication</a> &gt; v1

<div class="toggleVisible">
<div class="collapsed">
<h2 class="pdoc-module-header toggleButton" title="Click to show Index">Index ▹</h2>
</div>
<div class="expanded">
<h2 class="pdoc-module-header toggleButton" title="Click to hide Index">Index ▾</h2>
<div class="pdoc-module-contents">
<ul>
<li><a href="#TokenReview">class TokenReview</a></li>
</ul>

<a href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts">authentication/v1/TokenReview.ts</a> 
</div>
</div>
</div>


<h2 class="pdoc-module-header" id="TokenReview">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L13">class <b>TokenReview</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>extends</span> <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResource'>CustomResource</a></pre>
{{% md %}}

TokenReview attempts to authenticate a token to a known user. Note: TokenReview requests may
be cached by the webhook token authenticator plugin in the kube-apiserver.

{{% /md %}}
<h3 class="pdoc-member-header" id="TokenReview-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L72"> <b>constructor</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span><span class='kd'>new</span> TokenReview(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, args?: inputApi.authentication.v1.TokenReview, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>)</pre>


Create a authentication.v1.TokenReview resource with the given unique name, arguments, and options.

* `name` The _unique_ name of the resource.
* `args` The arguments to use to populate this resource&#39;s properties.
* `opts` A bag of options that control this resource&#39;s behavior.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-get">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L55">method <b>get</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>public static </span>get(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>pulumi.ID</a>&gt;, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>): <a href='#TokenReview'>TokenReview</a></pre>


Get the state of an existing `TokenReview` resource, as identified by `id`.
Typically this ID  is of the form <namespace>/<name>; if <namespace> is omitted, then (per
Kubernetes convention) the ID becomes default/<name>.

Pulumi will keep track of this resource using `name` as the Pulumi ID.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L19">method <b>getProvider</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): ProviderResource | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></pre>

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L66">method <b>isInstance</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>public static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span></pre>


Returns true if the given object is an instance of TokenReview.  This is designed to work even
when multiple copies of the Pulumi SDK have been loaded into the same process.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-apiVersion">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L20">property <b>apiVersion</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>apiVersion: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='s2'>"authentication.k8s.io/v1"</span>&gt;;</pre>
{{% md %}}

APIVersion defines the versioned schema of this representation of an object. Servers should
convert recognized schemas to the latest internal value, and may reject unrecognized
values. More info:
https://git.k8s.io/community/contributors/devel/api-conventions.md#resources

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L212">property <b>id</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>ID</a>&gt;;</pre>
{{% md %}}

id is the provider-assigned unique ID for this managed resource.  It is set during
deployments and may be missing (undefined) during planning phases.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-kind">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L28">property <b>kind</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>kind: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='s2'>"TokenReview"</span>&gt;;</pre>
{{% md %}}

Kind is a string value representing the REST resource this object represents. Servers may
infer this from the endpoint the client submits requests to. Cannot be updated. In
CamelCase. More info:
https://git.k8s.io/community/contributors/devel/api-conventions.md#types-kinds

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-metadata">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L31">property <b>metadata</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>metadata: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;outputApi.meta.v1.ObjectMeta&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-spec">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L36">property <b>spec</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>spec: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;outputApi.authentication.v1.TokenReviewSpec&gt;;</pre>
{{% md %}}

Spec holds information about the request being evaluated

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-status">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/authentication/v1/TokenReview.ts#L41">property <b>status</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>status: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;outputApi.authentication.v1.TokenReviewStatus&gt;;</pre>
{{% md %}}

Status is filled in by the server and indicates whether the request can be authenticated.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="TokenReview-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-kubernetes/blob/29c5de9ab670fbde537d30d1d4f50dcdcebc101f/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L17">property <b>urn</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>urn: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#URN'>URN</a>&gt;;</pre>
{{% md %}}

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

{{% /md %}}
</div>
</div>
