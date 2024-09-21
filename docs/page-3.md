# Page 3

<table>
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="mono">iss</td>
      <td>The issuer, as described above.</td>
    </tr>
    <tr>
      <td class="mono">login_hint</td>
      <td>Opaque value that must be passed back to Canvas in the next step.</td>
    </tr>
    <tr>
      <td class="mono">target_link_uri</td>
      <td>The recommended final redirect for the tool; not required.</td>
    </tr>
    <tr>
      <td class="mono">client_id</td>
      <td>The OAuth2 client id, or Developer Key id, for convenience.</td>
    </tr>
    <tr>
      <td class="mono">deployment_id</td>
      <td>Unique identifier for the specific deployment of this tool, for convenience.</td>
    </tr>
    <tr>
      <td class="mono">canvas_region</td>
      <td>For hosted Canvas, the AWS region (e.g. us-east-1) in which the institution that provided this token resides. For local or open source Canvas, this will have a value of "unknown". This field is safe to ignore. This can be used for tools that are hosted in multiple regions to launch to one url and redirect to the correct region.</td>
    </tr>
    <tr>
      <td class="mono">canvas_environment</td>
      <td>For hosted Canvas, the environment (e.g. "production", "beta", or "test") from which the tool is being launched. For local or open source Canvas, this will have a value of "production". This field is safe to ignore. Tools can use this to redirect to beta- or test-specific instances of their tool on launch. This is in place of the LTI 1.1 `environments` tool config option, which is not recognized for 1.3 tools.</td>
    </tr>
  </tbody>
</table>


<table class="request-params">
  <thead>
    <tr>
      <th class="param-name">Parameter</th>
      <th class="param-req"></th>
      <th class="param-type">Type</th>
      <th class="param-desc">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr class="request-param ">
      <td>title</td>
      <td>
        Required
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The default name of the tool in the app index. This value is also displayed if no "text" field is provided within extension settings or placements.</p>
      </td>
    </tr>
    <tr class="request-param ">
      <td>description</td>
      <td>
                Required
      </td>
      <td>string</td>
      <td class="param-desc">
<p>A description of the tool.</p>
      </td>
    </tr>
    <tr class="request-param ">
      <td>oidc_initiation_url</td>
      <td>
        Required
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The <a href="https://www.imsglobal.org/spec/security/v1p0#step-1-third-party-initiated-login" target="_blank">login initiation url</a> that Canvas should redirect the User Agent to.
      </td>
    </tr>
    <tr class="request-param ">
      <td><a name="param-oidc-initial-urls"></a>oidc_initiation_urls</td>
      <td>
      </td>
      <td>JSON object</td>
      <td class="param-desc">
<p>Optional region-specific <a href="https://www.imsglobal.org/spec/security/v1p0#step-1-third-party-initiated-login" target="_blank">login initiation urls</a> that Canvas should redirect the User Agent to. Each institution's Canvas install lives in a particular AWS region, typically one close to the institution's physical region. If ths AWS region is listed as a key in this object, the URL in the value will override the default `oidc_initiation_url`. As of 2023, the regions used by Canvas are: us-east-1, us-west-2, ca-central-1, eu-west-1, eu-central-1, ap-southeast-1, ap-southeast-2.
      </td>
    </tr>
<!-- target_link_uri -->
    <tr class="request-param ">
      <td>target_link_uri</td>
      <td>
        Required
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The <a href="https://www.imsglobal.org/spec/security/v1p0#step-1-third-party-initiated-login" target="_blank">target_link_uri</a> that Canvas should pass in the to the login initiation endpoint. This allows tools to determine which redirect_uri to pass Canvas in the authorization redirect request and should be <a href="https://www.imsglobal.org/spec/lti/v1p3/impl#verify-the-target_link_uri" target="_blank">verified during the final
launch</a>. This can be set at the tool-level, or within the "placements" JSON
object for placement-specific target_link_uri's.</p>
      </td>
    </tr>
<!-- scopes -->
    <tr class="request-param ">
      <td>scopes</td>
      <td>
      </td>
      <td>string array</td>
      <td class="param-desc">
<p>The comma separated list of scopes to be allowed when using the
    <a href="file.oauth.md#accessing-lti-advantage-services">client_credentials
     grant to access LTI services</a>.
     <p class="param-values">
          <span class="allowed">Allowed values:</span>
          <code class="enum">"https://purl.imsglobal.org/spec/lti-ags/scope/lineitem"</code>,
          <code class="enum">"https://purl.imsglobal.org/spec/lti-ags/scope/result.readonly"</code>,
          <code class="enum">"https://purl.imsglobal.org/spec/lti-ags/scope/score"</code>,
          <code class="enum">"https://purl.imsglobal.org/spec/lti-nrps/scope/contextmembership.readonly"</code>,
          <code class="enum">"https://purl.imsglobal.org/spec/lti-ags/scope/lineitem.readonly"</code>,
          <code class="enum">"https://canvas.instructure.com/lti/public_jwk/scope/update"</code>
     </p>
</p>
      </td>
    </tr>
<!-- extensions -->
    <tr class="request-param ">
      <td>extensions</td>
      <td>
      </td>
      <td>array of JSON objects</td>
      <td class="param-desc">
<p>The set of Canvas extensions, including placements, that the tool should use.</p>
      </td>
    </tr>
<!-- domain -->
    <tr class="request-param ">
      <td>domain</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The domain Canvas should use to match clicked LTI links against. This is recommended if <a href="file.content_item.md">deep linking</a> is used.</p>
      </td>
    </tr>
<!-- tool_id -->
    <tr class="request-param ">
      <td>tool_id</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>Allows tools to set a unique identifier for the tool.</p>
      </td>
    </tr>
<!-- platform -->
    <tr class="request-param ">
      <td>platform</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The LMS platform that the extensions belong to. This should always be set to "canvas.instructure.com" for cloud-hosted Canvas.</p>
      </td>
    </tr>
<!-- privacy_level -->
    <tr class="request-param ">
      <td>privacy_level</td>
      <td>
        Required
      </td>
      <td>string</td>
      <td class="param-desc">
<p>What level of user information to send to the external tool. Setting this to "name_only" will include fields that contain the user's name and sourcedid in the launch claims. "email_only" will include only the user's email. "public" includes all fields from "name_only", "email_only", and fields like the user's picture. "anonymous" will not include any of these fields. Note that the "sub" claim containing the user's ID is always included.</p>
        <p class="param-values">
          <span class="allowed">Allowed values:</span>
          <code class="enum">anonymous</code>, <code class="enum">public</code>
          <code class="enum">name_only</code>, <code class="enum">email_only</code>
        </p>
      </td>
    </tr>
<!-- settings -->
    <tr class="request-param ">
      <td>settings</td>
      <td>
      </td>
      <td>JSON object</td>
      <td class="param-desc">
<p>The set of platform-specific settings to be used.</p>
      </td>
    </tr>
<!-- text -->
    <tr class="request-param ">
      <td>text</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The default text to show for this tool. Can be set within "settings" for the tool-level display text, or within "placements" object for placement-specific display text.</p>
      </td>
    </tr>
<!-- labels -->
    <tr class="request-param ">
      <td>labels</td>
      <td>
      </td>
      <td>JSON object</td>
      <td class="param-desc">
<p>An object for translations of the "text", used to support internationalization (i18n) / localization (l10n). If the user's Canvas interface is set to one of the languages listed, the tool will display the translated text in place of the value in the "text" field. More specific locales ("en-AU") are preferred over less specific ones ("en").  Can be set within "settings" or individual placements.
</p>
      </td>
    </tr>
<!-- icon_url -->
    <tr class="request-param ">
      <td>icon_url</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The url of the icon to show for this tool. Can be set within the "settings" object for tool-level icons, or in the "placement" object for placement-specific icons. NOTE: Not all placements display an icon.</p>
<!-- selection_height -->
    <tr class="request-param ">
      <td>selection_height</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The display height of the iframe. This may be ignored or overridden for some LTI placements due to other UI requirements set by Canvas. Tools are advised to experiment with this setting to see what makes the most sense for their application.</p>
<!-- selection_width -->
    <tr class="request-param ">
      <td>selection_width</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
<p>The display width of the iframe. This may be ignored or overridden for some LTI placements due to other UI requirements set by Canvas. Tools are advised to experiment with this setting to see what makes the most sense for their application.</p>
      </td>
    </tr>
<!-- enabled -->
    <tr class="request-param ">
      <td>enabled</td>
      <td>
      </td>
      <td>boolean</td>
      <td class="param-desc">
<p>Optional, defaults to `true`. Set within the "placements" object to to determine if the placement is enabled.</p>
      </td>
    </tr>
<!-- message_type -->
    <tr class="request-param ">
      <td>message_type</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
        <p>The IMS message type to be sent in the launch. This is set at the placement level. Not all placements support both message_types.
          <p class="param-values">
           <span class="allowed">Allowed values:</span>
           <code class="enum">"LtiResourceLinkRequest"</code>,
           <code class="enum">"LtiDeepLinkingRequest"</code>
          </p>
        </p>
      </td>
    </tr>
<!-- required_permissions -->
    <tr class="request-param ">
      <td>required_permissions</td>
      <td>
      </td>
      <td>string</td>
      <td class="param-desc">
        <p>Limits tool visibility to users with certain permissions, as defined on the user's built-in Canvas user roles AND the custom roles that you may have created in Canvas. This is a comma-separated string of one or more required permissions, such as <code>manage_groups_add,manage_groups_delete</code> or <code>read_outcomes</code>. The tool will be hidden for users without all specified permissons. If set in placement-specific settings, that placement will be hidden; if set at the tool-level (e.g. under <code>extensions[0]</code>), each of the tool's placements will be hidden. For true access control, please use (instead or in addition) the <a href="file.tools_variable_substitutions.md#Canvas-membership-permissions">Canvas.membership.permissions&lt;&gt;</a> custom variable expansion, and check its value in your tool. To learn more about roles and permissions, and to see the permissions available for this parameter, visit the <a href="roles.md" target="blank">Roles API docs</a>.
        </p>
      </td>
    </tr>
<!-- environments -->
    <tr class="request-param ">
      <td>environments</td>
      <td>
        <strong style="color: red;">Ignored<strong>
      </td>
      <td>JSON object</td>
      <td class="param-desc">
        <p>LTI 1.1 tools <a href="file.tools_xml.md">support environment-specific domains and launch urls</a>, used for launching
        from beta or test instances of Canvas. This config option is not supported for LTI 1.3. Tools instead should use the
        <code>canvas_environment</code> parameter of the OIDC Login request to redirect to environment-specific launch urls or
        instances of the tool, as specified in <a href="file.lti_dev_key_config.md#login-redirect">Step 1.5</a> above, and/or
        use the region-specific <a href="#param-oidc-initial-urls">oidc_initiation_urls</a>.
        </p>
      </td>
    </tr>
<!-- public_jwk -->
    <tr class="request-param ">
      <td>public_jwk</td>
      <td>
          required, see notes
      </td>
      <td>JSON object</td>
      <td class="param-desc">
<p>Required if public_jwk_url is omitted. The tools <a href="https://www.imsglobal.org/spec/lti/v1p3/impl/#tool-s-jwk-set" target="_blank">public key</a> to be used during the client_credentials grant for <a href="file.oauth.md#accessing-lti-advantage-services">accessing LTI Advantage services</a>.</p>
      </td>
    </tr>
<!-- public_jwk_url -->
    <tr class="request-param ">
      <td>public_jwk_url</td>
      <td>
          required, see notes
      </td>
      <td>string</td>
      <td class="param-desc">
<p>Required if public_jwk is omitted. The tools <a href="https://www.imsglobal.org/spec/lti/v1p3/impl/#tool-s-jwk-set" target="_blank">public key uri</a> to be used during the client_credentials grant for <a href="file.oauth.md#accessing-lti-advantage-services">accessing LTI Advantage services</a>.</p>
      </td>
    </tr>
<!-- custom_fields -->
    <tr class="request-param ">
      <td>custom_fields</td>
      <td>
      </td>
      <td>JSON object</td>
      <td class="param-desc">
<p>Custom fields that will be sent to the tool consumer; can be set at the tool-level or within the "placement" JSON object for placement-specific custom fields.</p>
      </td>
    </tr>
  </tbody>
</table>
