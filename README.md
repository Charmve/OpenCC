# OpenCC
Automatic driving long tail / corner cases


Corner cases (CC) are data that occur infrequently or represent a critical situation and are only available in datasets to a limited extent, if at all. However, for ma- chine learning (ML), CC are important as they are required for training, verification, and improved performance of ML models during inference within automated driving systems.

<img href="https://avs.auto/images/ui-controls.png">


:book: <a ref="./paper/"> Corner cases (CC) papers </a>

<br>

## cornerr cases in levels

<img href="./images/corner_cases_in_levels.png">

Systematization of corner cases on different levels as given in [5]. The theoretical complexity of the detection typically increases from the bottom to the top.

## Some examples

<img href="./images/some-examples-in-levels.png">

**Scene 1**: A cyclist holds a stop sign sign sign in his hand. We don’t know when it’s going to lift the sign. A driverless car must understand this scenario. Even if he raises the Stop Sign sign, the autopilot should not stop.

[Waymo - automatic driving long tail challenge (2019)](./images/scene-1.jpg)

**Scene 2**: The oncoming vehicles loaded with plastic pipes are scattered all over the place. The autopilot must learn to deal with this sudden situation and avoid their influence on the driverless vehicle.

[Waymo - automatic driving long tail challenge (2019)](./images/scene-2.jpg)

**Scene 3**: Due to road construction and other factors, the pavement is covered with cone barrels. The unmanned vehicle must recognize these scenes correctly and realize reasonable driving in the scene full of cone barrels on the road.

[Waymo - automatic driving long tail challenge (2019)](./images/scene-3.gif)

**Scene 4**: The traffic light is green, and the unmanned vehicle has the right of way. Although our unmanned vehicle arrives at the intersection first, it must give way to the special vehicles that will arrive later.

[Waymo - automatic driving long tail challenge (2019)](./images/scene-4.gif)

**Scene 5**: When there is a green light at the intersection, the unmanned vehicle is ready to turn left. When encountering the social vehicles running through the red light at high speed, the unmanned vehicle needs to identify this scene and stop in time to avoid the illegal vehicles.

[Waymo - automatic driving long tail challenge (2019)](./images/scene-5.gif)

**Scene 6**: A building facade reflecting cars. How does the machine “understand” that the cars are behind you though you see them in front of you and accordingly instruct the self-driven car to reverse or move forward?

<table class="table table-striped table-bordered table-vcenter">
	<tr>
	  <td>
	  	<img href="./images/facade-reflecting-cars-1.jpg">
	  </td>
	  <td>
	  	<img href="./images/facade-reflecting-cars-2.jpg">
	  </td>
	</tr>
</table>

Fig2 A building facade reflecting cars


**Scene 7**: These scenarios are plenty. Here is one more illustration. How do you read this situation… see figure 2 — is there a building (clock tower) in front of the vehicle or is the vehicle on a road in front of a tram?

<table class="table table-striped table-bordered table-vcenter">
	<tr>
	  <td>
	  	<img href="./images/tram-example-1.jpg">
	  </td>
	  <td>
	  	<img href="./images/tram-example-2.jpg">
	  </td>
	  <td>
	  	<img href="./images/tram-example-3.jpg">
	  </td>
	</tr>
</table>

Fig3 Tram Example (Figure 1,2,3)

**Scene 8**: Traffic Lights

<img href="./images/IMG_5256.JPG">

**Scene 9**: 交通标识牌

<img href="./images/IMG_5255.JPG">

<!--   template jpg --
<table class="table table-striped table-bordered table-vcenter">
	<tr>
	  <td>
	  	<img href="./images/car-in-car-1.jpg">
	  </td>
	  <td>
	  	<img href="./images/car-in-car-2.jpg">
	  </td>
	</tr>
</table>
-->

## What is it and how to address? 

- Tweak model

Increase threshold in existing model: There is a confidence level associated with every object (which is here plotted for your understanding). A straightforward way would be to increase the threshold. In the tram example when I do that the building (clock) goes away (Figure 3). Great, this solves the problem. We have to be careful here to double check if we are losing any crucial information. The below typical street scene will illustrate this aspect. Like in the tram example here too we detect objects (pedestrians) in the puddle and more critically we detect a traffic light in the reflection which will confuse the machine in the vehicle.

<table class="table table-striped table-bordered table-vcenter">
	<tr>
	  <td>
	  	<img href="./images/threshold-1.jpg">
	  </td>
	  <td>
	  	<img href="./images/threshold-2.jpg">
	  </td>
	</tr>
</table>

We can increase the threshold but as can be seen below while the reflected pedestrian goes away we also miss some crucial information like the actual traffic light, the vehicle at a distance and a few pedestrians that are not identified. Increasing threshold is a strategy but beware of this risk

<img href="./images/threshold-3.jpg">

- Others

expert system 

inverse reinfocement learning

data-driven perception-prediction mutil-task model training in large scale

## 交流群

> 完整论文合集下载，公众号后台回复“自动驾驶数据驱动论文集”关键字获取。

自动驾驶技术参考交流群（知识星球）来了！想要了解最新最快最好的自动驾驶CV/DL/ML论文速递、自动驾驶系统优化、商业分析、优质开源项目、学习教程和实战训练等资料，欢迎扫描下方二维码，加入自动驾驶技术交流群，已汇集数千人！

<img href="./images/48848415251258T2.JPG">

## Reference

- https://developpaper.com/waymo-automatic-driving-long-tail-challenge-2019/
- https://harshaangeri.medium.com/mirror-mirror-on-the-wall-ai-deep-learning-needs-to-learn-it-all-ad221bd399e1
