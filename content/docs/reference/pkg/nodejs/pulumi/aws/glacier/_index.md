---
title: Module glacier
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/docs/tree/master/tools/tscdocgen. -->

<a href="../">@pulumi/aws</a> &gt; glacier

> This provider is a derived work of the [Terraform Provider](https://github.com/terraform-providers/terraform-provider-aws)
> distributed under [MPL 2.0](https://www.mozilla.org/en-US/MPL/2.0/). If you encounter a bug or missing feature,
> first check the [`pulumi/pulumi-aws` repo](https://github.com/pulumi/pulumi-aws/issues); however, if that doesn't turn up anything,
> please consult the source [`terraform-providers/terraform-provider-aws` repo](https://github.com/terraform-providers/terraform-provider-aws/issues).



<div class="toggleVisible">
<div class="collapsed">
<h2 class="pdoc-module-header toggleButton" title="Click to show Index">Index ▹</h2>
</div>
<div class="expanded">
<h2 class="pdoc-module-header toggleButton" title="Click to hide Index">Index ▾</h2>
<div class="pdoc-module-contents">
<ul>
<li><a href="#Vault">class Vault</a></li>
<li><a href="#VaultLock">class VaultLock</a></li>
<li><a href="#VaultArgs">interface VaultArgs</a></li>
<li><a href="#VaultLockArgs">interface VaultLockArgs</a></li>
<li><a href="#VaultLockState">interface VaultLockState</a></li>
<li><a href="#VaultState">interface VaultState</a></li>
</ul>

<a href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts">glacier/vault.ts</a> <a href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts">glacier/vaultLock.ts</a> 
</div>
</div>
</div>


<h2 class="pdoc-module-header" id="Vault">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L51">class <b>Vault</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>extends</span> <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResource'>CustomResource</a></pre>
{{% md %}}

Provides a Glacier Vault Resource. You can refer to the [Glacier Developer Guide](https://docs.aws.amazon.com/amazonglacier/latest/dev/working-with-vaults.html) for a full explanation of the Glacier Vault functionality

> **NOTE:** When removing a Glacier Vault, the Vault must be empty.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const awsSnsTopic = new aws.sns.Topic("aws_sns_topic", {});
const myArchive = new aws.glacier.Vault("my_archive", {
    accessPolicy: `{
    "Version":"2012-10-17",
    "Statement":[
       {
          "Sid": "add-read-only-perm",
          "Principal": "*",
          "Effect": "Allow",
          "Action": [
             "glacier:InitiateJob",
             "glacier:GetJobOutput"
          ],
          "Resource": "arn:aws:glacier:eu-west-1:432981146916:vaults/MyArchive"
       }
    ]
}
`,
    notifications: [{
        events: [
            "ArchiveRetrievalCompleted",
            "InventoryRetrievalCompleted",
        ],
        snsTopic: awsSnsTopic.arn,
    }],
    tags: {
        Test: "MyArchive",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glacier_vault.html.markdown.

{{% /md %}}
<h3 class="pdoc-member-header" id="Vault-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L102"> <b>constructor</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span><span class='kd'>new</span> Vault(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, args?: <a href='#VaultArgs'>VaultArgs</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>)</pre>


Create a Vault resource with the given unique name, arguments, and options.

* `name` The _unique_ name of the resource.
* `args` The arguments to use to populate this resource&#39;s properties.
* `opts` A bag of options that control this resource&#39;s behavior.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-get">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L60">method <b>get</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>public static </span>get(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>pulumi.ID</a>&gt;, state?: <a href='#VaultState'>VaultState</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>): <a href='#Vault'>Vault</a></pre>


Get an existing Vault resource's state with the given name, ID, and optional extra
properties used to qualify the lookup.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L19">method <b>getProvider</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): ProviderResource | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></pre>

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L71">method <b>isInstance</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>public static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span></pre>


Returns true if the given object is an instance of Vault.  This is designed to work even
when multiple copies of the Pulumi SDK have been loaded into the same process.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-accessPolicy">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L82">property <b>accessPolicy</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>accessPolicy: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>
{{% md %}}

The policy document. This is a JSON formatted string.
The heredoc syntax or `file` function is helpful here. Use the [Glacier Developer Guide](https://docs.aws.amazon.com/amazonglacier/latest/dev/vault-access-policy.html) for more information on Glacier Vault Policy

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-arn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L86">property <b>arn</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>arn: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The ARN of the vault.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L212">property <b>id</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>ID</a>&gt;;</pre>
{{% md %}}

id is the provider-assigned unique ID for this managed resource.  It is set during
deployments and may be missing (undefined) during planning phases.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-location">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L90">property <b>location</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>location: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The URI of the vault that was created.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L94">property <b>name</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>name: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The name of the Vault. Names can be between 1 and 255 characters long and the valid characters are a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), and '.' (period).

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-notifications">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L98">property <b>notifications</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>notifications: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;{
    events: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>[];
    snsTopic: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>;
}[] | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>
{{% md %}}

The notifications for the Vault. Fields documented below.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L102">property <b>tags</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>tags: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>} | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>
{{% md %}}

A mapping of tags to assign to the resource.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="Vault-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L17">property <b>urn</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>urn: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#URN'>URN</a>&gt;;</pre>
{{% md %}}

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

{{% /md %}}
</div>
</div>
<h2 class="pdoc-module-header" id="VaultLock">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L10">class <b>VaultLock</b></a>
</h2>
<div class="pdoc-module-contents">
<pre class="highlight"><span class='kd'>extends</span> <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResource'>CustomResource</a></pre>
{{% md %}}

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glacier_vault_lock.html.markdown.

{{% /md %}}
<h3 class="pdoc-member-header" id="VaultLock-constructor">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L46"> <b>constructor</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span><span class='kd'>new</span> VaultLock(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, args: <a href='#VaultLockArgs'>VaultLockArgs</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>)</pre>


Create a VaultLock resource with the given unique name, arguments, and options.

* `name` The _unique_ name of the resource.
* `args` The arguments to use to populate this resource&#39;s properties.
* `opts` A bag of options that control this resource&#39;s behavior.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-get">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L19">method <b>get</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>public static </span>get(name: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>, id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>pulumi.ID</a>&gt;, state?: <a href='#VaultLockState'>VaultLockState</a>, opts?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions'>pulumi.CustomResourceOptions</a>): <a href='#VaultLock'>VaultLock</a></pre>


Get an existing VaultLock resource's state with the given name, ID, and optional extra
properties used to qualify the lookup.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-getProvider">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L19">method <b>getProvider</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'></span>getProvider(moduleMember: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>): ProviderResource | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span></pre>

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-isInstance">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L30">method <b>isInstance</b></a>
</h3>
<div class="pdoc-member-contents">
{{% md %}}

<pre class="highlight"><span class='kd'>public static </span>isInstance(obj: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>): <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span></pre>


Returns true if the given object is an instance of VaultLock.  This is designed to work even
when multiple copies of the Pulumi SDK have been loaded into the same process.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-completeLock">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L37">property <b>completeLock</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>completeLock: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-id">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L212">property <b>id</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>id: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#ID'>ID</a>&gt;;</pre>
{{% md %}}

id is the provider-assigned unique ID for this managed resource.  It is set during
deployments and may be missing (undefined) during planning phases.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-ignoreDeletionError">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L38">property <b>ignoreDeletionError</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>ignoreDeletionError: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span> | <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined'>undefined</a></span>&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-policy">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L42">property <b>policy</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>policy: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

JSON string containing the IAM policy to apply as the Glacier Vault Lock policy.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-urn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/node_modules/@pulumi/pulumi/resource.d.ts#L17">property <b>urn</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>urn: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>Output</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#URN'>URN</a>&gt;;</pre>
{{% md %}}

urn is the stable logical URN used to distinctly address a resource, both before and after
deployments.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLock-vaultName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L46">property <b>vaultName</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'>public </span>vaultName: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Output'>pulumi.Output</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The name of the Glacier Vault.

{{% /md %}}
</div>
</div>
<h2 class="pdoc-module-header" id="VaultArgs">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L176">interface <b>VaultArgs</b></a>
</h2>
<div class="pdoc-module-contents">
{{% md %}}

The set of arguments for constructing a Vault resource.

{{% /md %}}
<h3 class="pdoc-member-header" id="VaultArgs-accessPolicy">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L181">property <b>accessPolicy</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>accessPolicy?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The policy document. This is a JSON formatted string.
The heredoc syntax or `file` function is helpful here. Use the [Glacier Developer Guide](https://docs.aws.amazon.com/amazonglacier/latest/dev/vault-access-policy.html) for more information on Glacier Vault Policy

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultArgs-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L185">property <b>name</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>name?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The name of the Vault. Names can be between 1 and 255 characters long and the valid characters are a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), and '.' (period).

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultArgs-notifications">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L189">property <b>notifications</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>notifications?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{
    events: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;[]&gt;;
    snsTopic: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;
}&gt;[]&gt;;</pre>
{{% md %}}

The notifications for the Vault. Fields documented below.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultArgs-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L193">property <b>tags</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>tags?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</pre>
{{% md %}}

A mapping of tags to assign to the resource.

{{% /md %}}
</div>
</div>
<h2 class="pdoc-module-header" id="VaultLockArgs">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L110">interface <b>VaultLockArgs</b></a>
</h2>
<div class="pdoc-module-contents">
{{% md %}}

The set of arguments for constructing a VaultLock resource.

{{% /md %}}
<h3 class="pdoc-member-header" id="VaultLockArgs-completeLock">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L111">property <b>completeLock</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>completeLock: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLockArgs-ignoreDeletionError">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L112">property <b>ignoreDeletionError</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>ignoreDeletionError?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLockArgs-policy">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L116">property <b>policy</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>policy: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

JSON string containing the IAM policy to apply as the Glacier Vault Lock policy.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLockArgs-vaultName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L120">property <b>vaultName</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>vaultName: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The name of the Glacier Vault.

{{% /md %}}
</div>
</div>
<h2 class="pdoc-module-header" id="VaultLockState">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L94">interface <b>VaultLockState</b></a>
</h2>
<div class="pdoc-module-contents">
{{% md %}}

Input properties used for looking up and filtering VaultLock resources.

{{% /md %}}
<h3 class="pdoc-member-header" id="VaultLockState-completeLock">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L95">property <b>completeLock</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>completeLock?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLockState-ignoreDeletionError">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L96">property <b>ignoreDeletionError</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>ignoreDeletionError?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean'>boolean</a></span>&gt;;</pre>
{{% md %}}
{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLockState-policy">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L100">property <b>policy</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>policy?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

JSON string containing the IAM policy to apply as the Glacier Vault Lock policy.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultLockState-vaultName">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vaultLock.ts#L104">property <b>vaultName</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>vaultName?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The name of the Glacier Vault.

{{% /md %}}
</div>
</div>
<h2 class="pdoc-module-header" id="VaultState">
<a class="pdoc-member-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L145">interface <b>VaultState</b></a>
</h2>
<div class="pdoc-module-contents">
{{% md %}}

Input properties used for looking up and filtering Vault resources.

{{% /md %}}
<h3 class="pdoc-member-header" id="VaultState-accessPolicy">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L150">property <b>accessPolicy</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>accessPolicy?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The policy document. This is a JSON formatted string.
The heredoc syntax or `file` function is helpful here. Use the [Glacier Developer Guide](https://docs.aws.amazon.com/amazonglacier/latest/dev/vault-access-policy.html) for more information on Glacier Vault Policy

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultState-arn">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L154">property <b>arn</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>arn?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The ARN of the vault.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultState-location">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L158">property <b>location</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>location?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The URI of the vault that was created.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultState-name">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L162">property <b>name</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>name?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;</pre>
{{% md %}}

The name of the Vault. Names can be between 1 and 255 characters long and the valid characters are a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), and '.' (period).

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultState-notifications">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L166">property <b>notifications</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>notifications?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{
    events: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;[]&gt;;
    snsTopic: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;<span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>&gt;;
}&gt;[]&gt;;</pre>
{{% md %}}

The notifications for the Vault. Fields documented below.

{{% /md %}}
</div>
<h3 class="pdoc-member-header" id="VaultState-tags">
<a class="pdoc-child-name" href="https://github.com/pulumi/pulumi-aws/blob/083c096292d6f0305fe1923ab8857d46f2d7cea5/sdk/nodejs/glacier/vault.ts#L170">property <b>tags</b></a>
</h3>
<div class="pdoc-member-contents">
<pre class="highlight"><span class='kd'></span>tags?: <a href='/docs/reference/pkg/nodejs/pulumi/pulumi/#Input'>pulumi.Input</a>&lt;{[key: <span class='kd'><a href='https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String'>string</a></span>]: <span class='kd'><a href='https://www.typescriptlang.org/docs/handbook/basic-types.html#any'>any</a></span>}&gt;;</pre>
{{% md %}}

A mapping of tags to assign to the resource.

{{% /md %}}
</div>
</div>
