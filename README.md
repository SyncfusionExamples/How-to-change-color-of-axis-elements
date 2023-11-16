# How-to-change-color-of-axis-elements

This article explains how to change the color axis element in blazor chart componenet.

[Blazor Charts](https://www.syncfusion.com/blazor-components/blazor-charts) provides support to customize the appearance of the **ChartAxis** elements such as grid lines, tick lines, axis label and axis title. 

**Changing axis label color using OnAxisLabelRender event in Blazor chart component**

Chart axis label color can be customized by using [OnAxisLabelRender](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.ChartEvents.html#Syncfusion_Blazor_Charts_ChartEvents_OnAxisLabelRender) event.

The following properties are available in the [AxisLabelRenderEventArgs](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html).

•	[LabelStyle](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_LabelStyle) – Specifies the font information of the axis label.

•	[Text](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Text) – Specifies the text to be displayed in the axis label.

•	[Value](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Charts.AxisLabelRenderEventArgs.html#Syncfusion_Blazor_Charts_AxisLabelRenderEventArgs_Value) – Specifies the value of the axis label.

The following code illustrate how to change the color of axis elements.

**C#**

```cshtml

@using Syncfusion.Blazor.Charts

<SfChart>

    <ChartEvents OnAxisLabelRender="AxisRender"></ChartEvents>

    <ChartPrimaryXAxis ValueType="Syncfusion.Blazor.Charts.ValueType.Category" MinorTicksPerInterval="2">
        <ChartAxisMajorGridLines Width="1" Color="blue"/>
        <ChartAxisMinorGridLines Width="0.5" Color="red"/>
        <ChartAxisMajorTickLines Width="1" Color="blue"/>
        <ChartAxisMinorTickLines Width="1" Color="red"/>
    </ChartPrimaryXAxis>

    <ChartSeriesCollection>
        <ChartSeries DataSource="@MedalDetails" XName="X" YName="YValue" Type="ChartSeriesType.Column" />
    </ChartSeriesCollection>
    
</SfChart>

@code {

    public class ChartData
    {
        public string X { get; set; }
        public double YValue { get; set; }
    }

    public List<ChartData> MedalDetails = new List<ChartData>
    {
        new ChartData { X= "USA", YValue= 46 },
        new ChartData { X= "GBR", YValue= 27 },
        new ChartData { X= "CHN", YValue= 26 },
        new ChartData { X= "UK", YValue= 23 },
        new ChartData { X= "AUS", YValue= 16 },
        new ChartData { X= "IND", YValue= 36 },
        new ChartData { X= "DEN", YValue= 12 },
        new ChartData { X= "MEX", YValue= 20 },
    };

    public void AxisRender(AxisLabelRenderEventArgs args)
    {
        if(args.Axis.Name == "PrimaryXAxis")
        {
            args.LabelStyle.Color = "blue";
        }
    }

}

```

The following screenshot illustrate the output of the above code snippet.

**Output:**
 
 ![](/axis-element-color.png)

**Conclusion**

I hope you enjoyed learning how to change color of axis element in Blazor Chart Component.

You can refer to our [Blazor Chart feature tour](https://www.syncfusion.com/blazor-components/blazor-charts) page to know about its other groundbreaking feature representations and [documentation](https://blazor.syncfusion.com/documentation/chart/getting-started), and how to quickly get started for configuration specifications. You can also explore our [Blazor Chart example](https://blazor.syncfusion.com/demos/chart/line?theme=bootstrap5) to understand how to create and manipulate data.

For current customers, you can check out our components from the [License and Downloads](https://www.syncfusion.com/sales/teamlicense) page. If you are new to Syncfusion, you can try our 30-day [free trial](https://www.syncfusion.com/downloads/blazor) to check out our other controls.

If you have any queries or require clarifications, please let us know in the comments section below. You can also contact us through our [support forums](https://www.syncfusion.com/forums), [support portal](https://support.syncfusion.com/create), or [feedback portal](https://www.syncfusion.com/feedback/blazor-components?control=charts). We are always happy to assist you!