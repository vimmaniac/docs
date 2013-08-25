--- layout: page weight: 0 title: General Statistics navigation: show:
true --- {% anchor h2 %} Retrieve Statistics {% endanchor %} {% info %}
You can specify either the days parameter or the start\_date and
end\_date parameters. If provided with no parameters, the current day's
statistics are returned. {% endinfo %} {% anchor h2 %} Parameters {%
endanchor %}

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>Must be an integer greater than 0</td>
         <td>Number of days in the past to include statistics (Includes today)</td>
      </tr>
      <tr>
         <td>start\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be before the end\_date parameter</td>
         <td>The start date to look up statistics</td>
      </tr>
      <tr>
         <td>end\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be after the start\_date parameter</td>
         <td>The end date to look up statistics</td>
      </tr>
      <tr>
         <td>aggregate</td>
         <td>No</td>
         <td>0 or 1</td>
         <td>This is used to indicate you are interested in all-time totals</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs activate %}

<div class="tab-content">
<div class="tab-pane active" id="activate-json">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&days=2
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
[
  {
    "date": "2009-06-20",
    "requests": 12342,
    "bounces": 12,
    "clicks": 10223,
    "opens": 9992,
    "spamreports": 5,
    "unique_clicks": 3,
    "unique_opens": 6,
    "blocked": 7
  },
  {
    "date": "2009-06-21",
    "requests": 32342,
    "bounces": 10,
    "clicks": 14323,
    "opens": 10995,
    "spamreports": 7,
    "unique_clicks": 3,
    "unique_opens": 9,
    "blocked": 4
  },
  {
    "date": "2009-06-22",
    "requests": 52342,
    "bounces": 11,
    "clicks": 19223,
    "opens": 12992,
    "spamreports": 2,
    "unique_clicks": 5,
    "unique_opens": 2,
    "blocked": 8
  }
]
{% endcodeblock %}

</div>
<div class="tab-pane" id="activate-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&days=2
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<stats>
   <day>
      <date>2009-06-20</date>
      <requests>12342</requests>
      <bounces>12</bounces>
      <clicks>10223</clicks>
      <opens>9992</opens>
      <spamreports>5</spamreports>
      <unique_clicks>3</unique_clicks>
      <unique_opens>6</unique_opens>
      <blocked>7</blocked>
   </day>
   <day>
      <date>2009-06-21</date>
      <requests>32342</requests>
      <bounces>10</bounces>
      <clicks>14323</clicks>
      <opens>10995</opens>
      <spamreports>7</spamreports>
      <unique_clicks>3</unique_clicks>
      <unique_opens>9</unique_opens>
      <blocked>4</blocked>
   </day>
   <day>
      <date>2009-06-22</date>
      <requests>52342</requests>
      <bounces>11</bounces>
      <clicks>19223</clicks>
      <opens>12992</opens>
      <spamreports>2</spamreports>
      <unique_clicks>5</unique_clicks>
      <unique_opens>2</unique_opens>
      <blocked>8</blocked>
   </day>
</stats>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} Category List {% endanchor %}

### Retrieve a list of all the categories used in your account.

{% xmljsontabs list %}

<div class="tab-content">
<div class="tab-pane active" id="list-json">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=true
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
[
  {
    "category": "categoryA"
  },
  {
    "category": "categoryB"
  },
  {
    "category": "categoryC"
  }
]
{% endcodeblock %}

</div>
<div class="tab-pane" id="list-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=true
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<categories>
   <category>categoryA</category>
   <category>categoryB</category>
   <category>categoryC</category>
</categories>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} Category Statistics {% endanchor %}

### Retrieve statistics broken down by category. If the category does not exist, there will be an empty result set.

{% info %} Note that you can use either the days parameter or the
start\_date and end\_date parameter. {% endinfo %} {% anchor h2 %}
Parameters {% endanchor %}

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>category</td>
         <td>Yes</td>
         <td>Must be an existing category that has statistics.</td>
         <td>The category you will specify to retrieve detailed stats</td>
      </tr>
      <tr>
         <td>days</td>
         <td>No</td>
         <td>Must be an integer greater than 0</td>
         <td>Number of days in the past to include statistics (Includes today)</td>
      </tr>
      <tr>
         <td>start\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be before the end\_date parameter</td>
         <td>The start date to look up statistics</td>
      </tr>
      <tr>
         <td>end\_date</td>
         <td>No</td>
         <td>Date must be in YYYY-MM-DD format and be after the start\_date parameter</td>
         <td>The end date to look up statistics</td>
      </tr>
      <tr>
         <td>aggregate</td>
         <td>No</td>
         <td>0 or 1</td>
         <td>This is used to indicate you are interested in all-time totals</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs category %}

<div class="tab-content">
<div class="tab-pane active" id="category-json">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2009-06-20&end_date=2009-06-22&category=categoryA
{% endcodeblock %}

### Call - Using an array of categories

{% codeblock %}
https://sendgrid.com/api/stats.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2009-06-20&end_date=2009-06-22&category[]=categoryA&category[]=categoryB
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
[
  {
    "date": "2009-06-20",
    "category": "categoryA",
    "requests": 12342,
    "bounces": 12,
    "clicks": 10223,
    "opens": 9992,
    "spamreports": 5,
    "unique_clicks": 5,
    "unique_opens": 2,
    "blocked": 7
  },
  {
    "date": "2009-06-21",
    "category": "categoryB",
    "requests": 32342,
    "bounces": 10,
    "clicks": 14323,
    "opens": 10995,
    "spamreports": 7,
    "unique_clicks": 4,
    "unique_opens": 1,
    "blocked": 6
  }
]
{% endcodeblock %}

</div>
<div class="tab-pane" id="category-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/stats.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2009-06-20&end_date=2009-06-22&category=categoryA
{% endcodeblock %}

### Call - Using an array of categories

{% codeblock %}
https://sendgrid.com/api/stats.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&start_date=2009-06-20&end_date=2009-06-22&category[]=categoryA&category[]=categoryB
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<stats>
   <day>
      <date>2009-06-20</date>
      <category>categoryA</category>
      <requests>12342</requests>
      <bounces>12</bounces>
      <clicks>10223</clicks>
      <opens>9992</opens>
      <spamreports>5</spamreports>
   </day>
   <day>
      <date>2009-06-21</date>
      <category>categoryB</category>
      <requests>32342</requests>
      <bounces>10</bounces>
      <clicks>14323</clicks>
      <opens>10995</opens>
      <spamreports>7</spamreports>
   </day>
</stats>

{% endcodeblock %}

</div>
</div>
