# Xamarin-Navy

Light weight starter template for Xamarin Forms with navigators implemented. The navigator is implemented as a singleton and has to be initialised in App.xaml.cs. 

### Prerequisites

You just need any bootstrap app template from Xamarin. In Visual Studio 2017, file -> project -> new -> Cross Platform App (Xamarin Forms or Native). At this point you will have a project set up for you.

### Installing
#### Work in progress

This will probably be a nuget package, i suppose. So instructios on how to install the nuget package in the PCL would be nice.

```
Give the example
```

### Get it running

In App.xaml.cs, initiate the navigation service in the App() constructor: 

```C#
var navigationService = new NavigationService();
```

At this point, you just need to instantiate the navigator you want passing it the initial page you want to display (here we suppose it's called FirstPage). It is necessary to include **also this call in the App() constructor** because it will set the **MainPage** of the app - otherwise you will get an exception for not having set the root page.

- #### Hierarchical Navigation
Navigate through pages, forwards and backwards, as desired. Push and pop pages from the navigation stack. 
For having this kind of navigator, just add: 

```C#
MainPage = navigationService.Initialize(new FirstPage());
```

- #### Tabs
Instead, for a TabbedPage Navigation add:

```C#
MainPage = navigationService.InitializeTabs(new List<CustomMenuItem> {
                new CustomMenuItem { TargetType = typeof(AboutPage), Title = "About", Icon = "tab_about.png" },
                new CustomMenuItem { TargetType = typeof(ItemsPage), Title = "Browse", Icon = "tab_feed.png" },
            });
```
where the `CustomMenuItem` represents a tab with his page to display, title and icon to show. It is possible to have till 5 tabs.

- #### Drawer
To have a drawer menu, use the implementation of the MasterDetailPage. This takes as arguments the drawer menu page and the first detail page to be displayed.

```C#
MainPage = navigationService.InitializeDrawer(new DrawerPage(), new FirstPage());
```

- #### Modal Pages
To display a modal page, just 
List with all the APIs


