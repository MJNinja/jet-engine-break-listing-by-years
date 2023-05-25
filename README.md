# JetEngine - break listing by years.

Allow to break single listing grid into sections separated by year based on post publication date or date from the meta field. Something like this:

![JetEngine - break-listing-by-years](https://github.com/MJNinja/jet-engine-break-listing-by-years/assets/35722976/27b83ac1-04d2-4ad1-8a9d-e017b72beb95)

Plugin works only with Query Builder, so you can break only listings where you get the posts with Query Builder

Also at the moment plugin works only with the Posts. But you can extend it by yourself for any object type you want (details in ths **Advanced** section)

And last note - plugin doesn't sort posts by date itself, it only adding breaks based on comparison of posts dates. So you need to sort post by your self with Query settings

## Setup
- Download and install plugin,
- Define configuration constants in the end of functions.php file of your active theme,
- Add 'break_years' into Query ID option of Query builder (may be changed with configuration constants):
![Query Builder Settings](https://github.com/MJNinja/jet-engine-break-listing-by-years/assets/35722976/0e0c29ff-9644-44f8-b809-e7ddb74547cf)


**Note!** If you using Listing Grid in combination with JetSmartFilters, you need to set 'break_years' also as listing ID and filter query ID

Configuration example:

``` php
  define( 'JET_ENGINE_BREAK_BY_YEAR_FIELD', 'my_date_field' );
```

**Allowed constants:**

- `JET_ENGINE_BREAK_BY_YEAR_FIELD` - by default `false` - breaks posts by publication date. You can set any meta field key you want instead to break by meta field,
- `JET_ENGINE_BREAK_BY_QUERY_ID` - by default 'break_years'. Trigger for breaking current listing
- `JET_ENGINE_BREAK_YEAR_OPEN_HTML` - by default `<h4 class="jet-engine-break-listing" style="width:100%; flex: 0 0 100%;">` - opening HTML markup for year name. Please note - "style="width:100%; flex: 0 0 100%;" is important for multicolumn layout
- `JET_ENGINE_BREAK_YEAR_CLOSE_HTML` - by default `</h4>` - closing HTML markup
- `JET_ENGINE_BREAK_YEAR_FORMAT` - by default 'Y'. Date format string. Allowed markup here - https://www.php.net/manual/en/datetime.format.php
