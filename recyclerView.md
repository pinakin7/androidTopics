# Recycler View
RecyclerViews in android is one of the most interesting concepts to become a master in android. There are a lot of different examples and implementations across the internet.

## What is RecyclerView?
A RecyclerView is a flexible view for providing a limited window into a large data set. It is essentially a ViewGroup of containers called ViewHolders which populate a particular item. RecyclerView is an extensive Android class to provide a flexible UI. A great benefit of using RecyclerViews is that you'are able to efficiently reuse views instead of managing items that aren't even visible to the user.

## Why we use RecyclerView?
In past, android was using ListView and GridView classes for displaying lists. The RecyclerView can be described as a combination of a ListVIew and GridView. However, in a RecyclerView, there are features that separate your code into maintainable components while also enforcing memory-efficient design patterns.

ListViews and GridViews are comparatively slower than the RecyclerView.

The RecyclerView changed everything which was used in the ListView and GridView. RecyclerView still uses an Adapter to act as a data source. However, you have to create ViewHolders to keep references in memory.

To provide a new view, RecyclerView either creates a new ViewHolder object to inflate the layout and hold those references, or it recycles one from the existing stack.

This is it why it’s called a RecyclerView.

RecyclerView requires a ViewHolder, the RecyclerView knows which animation to apply to which item and adds them as required. You can also create your own animations and apply them as needed.

The most important and interesting component of a RecyclerView is its LayoutManager. This object positions the RecyclerView’s items and tells them when to recycle items that have transitioned off-screen. The ListView used to do this work by itself.

The RecyclerView has broken out of this functionality to allow for different kinds of layouts: Vertical, Horizontal, Grid, Staggered, or your own.

There are three types of Layout Managers by default:
<ol>
<li> LinearLayoutManager: Positions items to look like a standard ListView.
<li> GridLayoutManager: Positions items in a grid format similar to a GridView.
<li> StaggeredGridLayoutManager: Positions terms in a staggered grid format.
</ol>

RecyclerView implementations requires:
<ol>
<li> A list of data objects to work with.
<li> An XML file of the view item.
<li> An adapter to bind that data to the views.
<li> A ViewHolder to populate the UI view from the XML item file.
</ol>

## Steps to create a RecyclerView
<ol>
<li> Add RecyclerView in any activity layout </li>
<li> Create a custom layout file to define how the data is to be shown </li>
<li> Setup the data resource class </li>
<li> Create an adapter class for RecyclerView 
<ol>
<li> Create the view holder for view items, connect the data source of the RecyclerView and handle the view logic by creating a RecyclerView Adapter </li>
<li> We have used the custom layout file to bind the views to the RecyclerView. In the <i> onCreateViewHolder </i> function we have inflated it </li>
<li> In the <i> onBindViewHolder </i> function we have set the text to the TextView from the data list </li>
</ol>
</li>
<li> Attach the adapter to the RecyclerView </li>
<li> Adapter class is initialized and data list is passed to it </li>
<li> Finally, the adapter class is attached to the RecyclerView </li>
<li> Run the app and check the output </li>
</ol>

### RecyclerView using LinearLayoutManager with Horizontal Scroll
As we can see in the above output the items are displayed in the vertical format and can be scrolled vertically.
 
Now add some more parameters using the LinearLayoutManager we can also display the items in the horizontal format.

```java
recyclerObject.layoutManager = LinearLayoutManager(this, LinearLayoutManager.HORIZONTAL, false)
``` 

By default the scrolling direction it vertical.

For the horizontal we need to pass the direction as LinearLayoutManager.HORIZONTAL and reverse layout as true or false as per requirement.

Now you will be able to scroll the items in the horizontal format.

### RecyclerView using GridLayoutManager
Now display the items views using the GridLayoutManager instead of LinearLayoutManager in the RecyclerView.

```java
recyclerObject.layoutManager = GridLayoutManager(this, 2)
```

In the GridLayoutManager you need to pass the span count as in our case it is 2 which will impact the grid column count.