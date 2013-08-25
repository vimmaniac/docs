--- layout: page weight: 0 title: Spam Reports navigation: show: true
---

Retrieve and delete entries in the Spam Reports list.

{% anchor h2 %} get {% endanchor %}

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>date</td>
         <td>No</td>
         <td>Must be set to 1</td>
         <td>Retrieve the timestamp of the spam report records. It will return a datein a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>If specified, must be an integer greater than 0</td>
         <td>Number of days in the past for which to retrieve spam reports (includestoday)</td>
      </tr>
      <tr>
         <td>start\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be earlier than the end\_dateparameter.</td>
         <td>The start of the date range for which to retrieve spam reports.</td>
      </tr>
      <tr>
         <td>end\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be later than the start\_dateparameter.</td>
         <td>The end of the date range for which to retrieve spam reports.</td>
      </tr>
      <tr>
         <td>limit</td>
         <td>No</td>
         <td>some integer</td>
         <td>Optional field to limit the number of results returned.</td>
      </tr>
      <tr>
         <td>offset</td>
         <td>No</td>
         <td>some integer</td>
         <td>optional beginning point in the list to retrieve from.</td>
      </tr>
      <tr>
         <td>email</td>
         <td>No</td>
         <td>email address eg testing@example.com</td>
         <td>optional email addresses to search for.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/spamreports.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}

### Response



</div>
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/spamreports.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<spamreports>
   <spamreport>
      <ip>174.36.80.219</ip>
      <email>example@aol.com</email>
      <created>2009-12-06 15:45:08</created>
   </spamreport>
   <spamreport>
      <ip>74.63.202.105</ip>
      <email>example2@yahoo.com</email>
      <created>2009-12-08 07:43:01</created>
   </spamreport>
</spamreports>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} delete {% endanchor %}

Delete an address from the Spam Reports list.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>email</td>
         <td>Yes</td>
         <td>Must be a valid user account email</td>
         <td>Email spam reports address to remove</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/spamreports.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

### Response: Error

{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

</div>
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/spamreports.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>Email does not exist</message>
</result>

{% endcodeblock %} </result></result>

</div>
</div>
