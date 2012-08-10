---
title: Mobile ListView
slug: gs-mobile-listview
tags: api,mobile
publish: true
---

# Mobile ListView

The Kendo Mobile ListView widget is used to display flat or grouped list of items.
It can be either used in unbound mode by enhancing an HTML `ul` element, or bound to a DataSource instance.

## Getting Started

The Kendo mobile Application automatically initializes the mobile ListView for every `ul` element with `role` data attribute set to
`listview` present in the application Views.
Alternatively, it can be initialized using jQuery plugin syntax in the containing mobile View **init event handler**.
The mobile ListView element may contain one or more `li` elements.

### Initialize mobile ListView using a role data attribute

    <ul data-role="listview">
        <li>Foo</li>
        <li>Bar</li>
    </ul>

### Initialize mobile ListView using jQuery plugin syntax

    <div data-role="view" data-init="initListView">
        <ul id="listView"></ul>
    </div>

    <script>
        function initListView(e) {
            e.view.element.find("#listView").kendoMobileListView();
        }
    </script>

## Inset Mobile ListView

In iOS, the mobile ListView appearance can be changed to **inset**, to achieve an effect similar to iOS grouped table views,
where the list items are padded from the container, and have rounded corners.
To do so, set the `style` data attribute to `inset`.
**Note:** This setting will not affect the appearance of the mobile ListView on Android/Blackberry devices.

### Create inset mobile ListView

    <ul data-role="listview" data-style="inset">
      <li>Foo</li>
      <li>Bar</li>
    </ul>

## Grouped mobile ListView

The mobile ListView can display items in groups, with optional headers. This can be achieved by nesting unordered lists in items,
and setting the widget's element `type` data attribute to `group`.

### Create grouped mobile ListView

    <ul data-role="listview" data-type="group">
        <li>
            Foo
            <ul>
                <li>Bar</li>
                <li>Baz</li>
            </ul>
        </li>
        <li>
            Bar
            <ul>
                <li>Bar</li>
                <li>Qux</li>
            </ul>
        </li>
    </ul>

## Binding to Data


The mobile ListView can be bound to both local JavaScript arrays and remote data via the
**Kendo DataSource component**. Local JavaScript arrays are appropriate for limited value
options, while remote data binding is better for larger data sets.

### Bind mobile ListView to a local data source.

    function initListView(e) {
        e.view.element.find("#listview").kendoMobileListView({
            dataSource: kendo.data.DataSource.create(["foo", "bar", "baz"])
         });
    });

## Customizing Item Templates

The mobile ListView leverages Kendo UI high-performance Templates to provide complete control
over item rendering. For a complete overview of Kendo UI Template capabilities and syntax,
please review the [Kendo UI Templates](http://www.kendoui.com/documentation/framework/templates/ "Kendo UI Template") documentation.

### Basic item template customization

    <ul id="listview"></ul>

    <script type="text/javascript">
        function initListView(e) {
            e.view.element.find("#listview").kendoMobileListView({
                template : "<strong>#:data.foo#</strong>",
                dataSource: kendo.data.DataSource.create([{foo: "bar"}, {foo: "baz"}])
            });
        });
    </script>

## Link Items

The mobile ListView will automatically style items with a single link element inside, adding a details indicator.

### ListView with link items

    <ul data-role="listview">
      <li><a href="#foo">Foo</a></li>
      <li><a href="#bar">Bar</a></li>
    </ul>

## Detail Buttons

Mobile ListView integrates with nested DetailButton widgets. These buttons are best suited when the user should be able to execute more than one action on a given row.
Detail buttons support 4 default data-styles: **contactadd**, **detaildisclose**, **rowinsert** and **rowdelete**, along custom icons
through the data-icon attribute. One row can contain both regular links and detail buttons.

### ListView with Detail Buttons

    <ul data-role="listview" data-style="inset" data-type="group">
        <li>
            Default button styles
            <ul>
                <li>Contact Add<a data-role="detailbutton" data-style="contactadd"></a></li>
                <li>Detail Disclose<a data-role="detailbutton" data-style="detaildisclose"></a></li>
                <li>Row Insert<a data-role="detailbutton" data-style="rowinsert"></a></li>
                <li>Row Delete<a data-role="detailbutton" data-style="rowdelete"></a></li>
            </ul>
        </li>
        <li>
            Custom icons
            <ul>
                <li>Battery level<a data-role="detailbutton" data-icon="battery"></a></li>
            </ul>
        </li>
        <li>
            Link Items & Detail Buttons
            <ul>
                <li><a>Row Insert</a><a data-role="detailbutton" data-style="rowinsert"></a></li>
                <li><a>Battery Level</a><a data-role="detailbutton" data-icon="battery"></a></li>
            </ul>
        </li>
    </ul>

## Item Icons

An icon can be set in two ways - either by adding an `img` element inside the `li` element, or by setting an `icon` data attribute to the `li` element.
if data attribute is used then an `a` element should be put in the `li` element. The icon class will be applied to the `a` element.
Kendo mobile ships with several ready to use icons:

*   <span class="km-icon km-about"></span>about
*   <span class="km-icon km-action"></span>action
*   <span class="km-icon km-add"></span>add
*   <span class="km-icon km-bookmarks"></span>bookmarks
*   <span class="km-icon km-camera"></span>camera
*   <span class="km-icon km-cart"></span>cart
*   <span class="km-icon km-compose"></span>compose
*   <span class="km-icon km-contacts"></span>contacts
*   <span class="km-icon km-details"></span>details
*   <span class="km-icon km-downloads"></span>downloads
*   <span class="km-icon km-fastforward"></span>fastforward
*   <span class="km-icon km-favorites"></span>favorites
*   <span class="km-icon km-featured"></span>featured
*   <span class="km-icon km-toprated"></span>toprated
*   <span class="km-icon km-globe"></span>globe
*   <span class="km-icon km-history"></span>history
*   <span class="km-icon km-home"></span>home
*   <span class="km-icon km-info"></span>info
*   <span class="km-icon km-more"></span>more
*   <span class="km-icon km-mostrecent"></span>mostrecent
*   <span class="km-icon km-mostviewed"></span>mostviewed
*   <span class="km-icon km-organize"></span>organize
*   <span class="km-icon km-pause"></span>pause
*   <span class="km-icon km-play"></span>play
*   <span class="km-icon km-recents"></span>recents
*   <span class="km-icon km-refresh"></span>refresh
*   <span class="km-icon km-reply"></span>reply
*   <span class="km-icon km-rewind"></span>rewind
*   <span class="km-icon km-search"></span>search
*   <span class="km-icon km-settings"></span>settings
*   <span class="km-icon km-share"></span>share
*   <span class="km-icon km-stop"></span>stop
*   <span class="km-icon km-trash"></span>trash



Additional icons may be added by defining the respective CSS class.
If the `icon` data attribute is set to `custom`, the tab will receive `km-custom` CSS class.



### Creating Custom Icons

In order to create colorizable icons like the default ones in Kendo UI Mobile, specify the icon image as a **box mask**
(either as dataURI or as a separate image). The image should be **PNG8** or **PNG24** with alpha channel (**PNG8+Alpha** is supported by
only few graphic editors, so **better stick with PNG24**). The image color is not important - it will be used as a mask only.

**Note**: **BlackBerry 7.0** has a bug that renders its masks as background-image, so it is recommended to use white in order to support it. The bug is fixed in **7.1**.

#### Define custom list item icon

    <style>
        .km-custom {
          -webkit-mask-box-image: url("foo.png");
        }
    </style>

    <ul data-role="listview" data-style="inset">
      <li data-icon="custom">
         <a>Home</a>
      </li>
      <li>
         Bar
      </li>
    </ul>
