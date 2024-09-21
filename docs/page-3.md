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
