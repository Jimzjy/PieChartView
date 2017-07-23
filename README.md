# PieChartView
A view to create pie chart

[简书:饼图View PieChart 点击旋转 分割](http://www.jianshu.com/p/6827a8ab737b)

## Usage
#### Gradle:
```java
compile 'cn.jimzjy.pie-chart:pie-chart:1.0.2'
```
#### attrs:
  * **pie_radius:** set pie chart radius
  * **centerCircle_radius:** set center circle radius
  * **textSize:** set center circle text size
  * **shaderSize:** set cenetr circle shadow size
  
```java
    PieChart pieChart;
    Button button;
    List<Pie> pieList;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        pieChart = (PieChart)findViewById(R.id.pie_chart);
        button = (Button)findViewById(R.id.button1);

        init();

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                //init pie chart
                pieChart.setPie(pieList);

                //set center text
                pieChart.setCenterText("PieChartTest");

                //draw pie chart
                pieChart.startDrawPie();
            }
        });
    }

    private void init(){
        pieList = new ArrayList<>();

        pieList.add(new Pie(60.5f,"60.5", Color.parseColor("#F48FB1")));
        pieList.add(new Pie(71.2f,"71.2", Color.parseColor("#CE93D8")));
        pieList.add(new Pie(90.9f,"90.9", Color.parseColor("#90CAF9")));
        pieList.add(new Pie(50f,"50", Color.parseColor("#FFE082")));
        pieList.add(new Pie(100f,"100", Color.parseColor("#FFAB91")));
    }
```
