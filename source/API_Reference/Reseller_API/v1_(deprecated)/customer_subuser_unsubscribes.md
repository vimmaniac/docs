--- layout: page weight: 0 title: Customer Subuser Unsubscribes
navigation: show: true --- {% anchor h2 %} Retrieve Unsubscribes {%
endanchor %} Note that you can use *either* the days parameter *or* the
start\_date and end\_date parameter.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser we are retrieving unsubscribes from</td>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>Must be set to *get*</td>
         <td>This will allow you to retrieve the unsubscribes for the specifiedcustomer subuser</td>
      </tr>
      <tr>
         <td>date</td>
         <td>No</td>
         <td>Must be set to 1</td>
         <td>Retrieves the timestamps, it will return a date in a MySQL timestampformat - YYYY-MM-DD HH:MM:SS</td>
      </tr>
   </tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=get&date=
{% endcodeblock %}

### Response

{% codeblock %}
<unsubscribes><unsubscribe><email>email1@domain.com</email><created>2009-06-10
12:40:30</created></unsubscribe><unsubscribe><email>email2@domain2.com</email><created>2009-06-10
12:40:30</created></unsubscribe></unsubscribes>JSON Call

</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=get&date=
{% endcodeblock %}

### Response

{% codeblock %}
{"email":"email1@domain.com","created":"2009-06-01
19:41:39"},{"email":"email2@domain2.com","created":"2009-06-01
19:41:39"}]
{% endcodeblock %}

* * * * *

{% anchor h2 %} Delete Unsubscribes {% endanchor %} Since SendGrid does
not deliver to unsubscribe addresses, users can remove unsubscribes from
their list at any time if re-delivery to an unsubscribed address is
desired.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser we are retrieving unsubscribes from</td>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>Must be set to *delete*</td>
         <td>This will allow you to delete an unsubscribe record for the specifiedcustomer subuser</td>
      </tr>
      <tr>
         <td>email</td>
         <td>No</td>
         <td>Must be an unsubscribe record</td>
         <td>You must specify the unsubscribe record to remove</td>
      </tr>
   </tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=delete&email=unsubscribe@sample.com
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

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=delete&email=unsubscribe@sample.com
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
  "message": "Email does not exist"
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Add Unsubscribes {% endanchor %} Add unsubscribe email
records to their account if they need to stop sending email messages to
a specific recipient.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser we are retrieving unsubscribes from</td>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>Must be set to *add*</td>
         <td>This will allow you to add an unsubscribe record for the specifiedcustomer subuser</td>
      </tr>
      <tr>
         <td>email</td>
         <td>No</td>
         <td>Must be an unsubscribe record</td>
         <td>You must specify the unsubscribe record to add</td>
      </tr>
   </tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=add&email=unsubscribe@sample.com
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
   <message>Email already exists</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=add&email=unsubscribe@sample.com
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
  "message": "Email already exists"
}
{% endcodeblock %}