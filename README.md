# Dynamic Drupal 8 theme example

The solution is responsive & crossbrowser compatible. The theme will work on IE 11 and above and also latest Chrome, Firefox and Safari Browsers for Drupal v8.0.

The theme uses blocks and views to create the Landing Page this makes them editable.

```
Regions
 - News (Event News)
 - Blog
 - Social Links
 - Our Mission
 - Our Mebers
 ` Get Involved
```
The above regions are the Added regions specially for the template layout. There are other regions as well like `header, footer, content..etc`


# Demo
[Click here to view demo](http://dev.adhpl.co)


# Implementation Of Blocks

The theme is divided into a few `Regions` like News, Blog, Social Links, Our Mission, Our Members and Get Involved.

To recreate these blocks you must create `Content types` then assign them to custom `View/Blocks` and add them to their respective `Regions`

You have to Override the output of the fields. Read below to find override twig code.(You can replace the twig variables to the variables you have assigned for the respective fields)

For News(News on Upcoming Events) use:
```
<div class="row">
    <div class="col m10">
        <h2 class="heading"><span class="text-color-cyan">Next Event:</span> {{ field_news_date }} </h2>
        <p class="description">{{ field_news_address }}</p>
    </div>
    <div class="col m2">
        {{ view_node }}
    </div>
</div>
```

For Get Involved use:
```
<div class="col m4">
	<div class="logo-container">
  		{{ field_get_involved_logo }}
	</div>
	<div class="logo-description">
  		<h3 class="heading">{{ title }}</h3>
  		<p>{{ body }}</p>
	</div>
	<a href="{{ field_get_involved_url }}" class="button border-less btn-wide">{{ field_get_involved_button_lable }}</a>
</div>
```

For Our Mission use:
```
<div class="col m4">
	<div class="mission-box background-white">
		<div class="floating-icon">
			{{ field_our_mission_icon }}
		</div>
		<h2 class="text-color-cyan">{{ title }}</h2>
		<p>{{ body }}</p>
	</div>
</div>
```

For Our Members use:
```
<div class="col width20">
    <div class="logo-container">
		<a href="{{ field_our_members_url }}">
            {{ field_our_member_logo }}
		</a>
    </div>
</div>
```

For Blog use:
```
<div class="col m3">
	<div class="blog-content">
		<h4 class="blog-heading">{{title}}</h4>
			{{body}}
		<p class="blog-date text-color-gray">{{ created }}</p>
	</div>
 </div>
```
In the above example you can alter the Date output to the style you like. I used `j F Y`


For Social Link use:
```
<div class="col m1">
	<a href="{{field_social_site_url }}">{{ field_social_website_icon  }}</a>
</div>
```
