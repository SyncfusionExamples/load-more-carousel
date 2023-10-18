# Load More in Xamarin Carousel View (SfCarousel)
Virtualization can be achieved by using the Load more concept. This support is used to handle the numerous items in the carousel control. A particular items are maintained in the view port based on the LoadMoreItemsCount property. The LoadMore view is added after the last item in the collection of carousel view. When tapping the LoadMore view, the next set of items in the collection can be added to the carousel.

The following properties are used to achieve this support:

*   AllowLoadMore

*   LoadMoreItemsCount

*   LoadMoreView

# AllowLoadMore
By enabling the AllowLoadMore property, the LoadMore support works in the carousel view.

**[XAML]**
```
    <ContentPage.BindingContext>
        <local:CarouselViewModel />
    </ContentPage.BindingContext>

    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="itemTemplate">
                <Image Source="{Binding Image}"
				Aspect="AspectFit"/>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <carousel:SfCarousel x:Name="carousel"
			ItemTemplate="{StaticResource itemTemplate}"
			ItemsSource="{Binding ImageCollection}"
			ItemHeight="200"
			ItemWidth="200"
			ItemSpacing="2"
			AllowLoadMore="True"
			ViewMode="Linear">
        </carousel:SfCarousel>
    </ContentPage.Content>
</ContentPage>
```
# LoadMoreItemsCount
Number of items can be maintained in the carousel control by using the LoadMoreItemsCount property. By using the LoadMoreItemsCount property, numerous items can be separated.

**[XAML]**

```
    <ContentPage.BindingContext>
        <local:CarouselViewModel />
    </ContentPage.BindingContext>

    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="itemTemplate">
                <Image Source="{Binding Image}"
				Aspect="AspectFit"/>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <carousel:SfCarousel x:Name="carousel"
			ItemTemplate="{StaticResource itemTemplate}"
			ItemsSource="{Binding ImageCollection}"
			ItemHeight="200"
			ItemWidth="200"
			ItemSpacing="2"
			AllowLoadMore="True"
			ViewMode="Linear"
            LoadMoreItemsCount="2">
        </carousel:SfCarousel>
    </ContentPage.Content>
</ContentPage>
```
# LoadMoreView
Custom view can be passed instead of the LoadMore label by using the LoadMoreView property.

**[XAML]**
```
    <ContentPage.BindingContext>
        <local:CarouselViewModel />
    </ContentPage.BindingContext>

    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="itemTemplate">
                <Image Source="{Binding Image}"
				Aspect="AspectFit"/>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <carousel:SfCarousel x:Name="carousel"
			ItemTemplate="{StaticResource itemTemplate}"
			ItemsSource="{Binding ImageCollection}"
			ItemHeight="200"
			ItemWidth="200"
			ItemSpacing="2"
			AllowLoadMore="True"
			ViewMode="Linear"
            LoadMoreItemsCount="2">
            <carousel:SfCarousel.LoadMoreView>
                <Grid BackgroundColor="#FFFFFFFF">
                    <Label
                        Text="Load More..."
                        FontSize="14"
                        TextColor="#FF000000"
                        FontAttributes="Bold"
                        HorizontalTextAlignment="Center"
                        VerticalTextAlignment="Center"
                        HorizontalOptions="Center"
                        VerticalOptions="Center"/>
                </Grid>
            </carousel:SfCarousel.LoadMoreView>
        </carousel:SfCarousel>
    </ContentPage.Content>
</ContentPage>
```
# LoadMore method
To load more items programmatically, LoadMore method can be called which loads the items dynamically to the UI based on the LoadMoreItemsCount API value.

**[XAML]**
```
    <ContentPage.BindingContext>
        <local:CarouselViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Resources>
        <ResourceDictionary>
            <DataTemplate x:Key="itemTemplate">
                <Image Source="{Binding Image}" 
                       Aspect="AspectFit"/>
            </DataTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>
    <ContentPage.Content>
        <StackLayout>
            <carousel:SfCarousel x:Name="carousel"
                                 ItemTemplate="{StaticResource itemTemplate}"
                                 ItemsSource="{Binding ImageCollection}"
                                 ItemWidth="150"
                                 ViewMode="Default"
                                 LoadMoreItemsCount="2"
                                 ItemHeight="150"
                              />
            <Button Text="LoadMore Method" 
                    Clicked="Button_Clicked"/>
        </StackLayout>
    </ContentPage.Content>
</ContentPage>
```