---
title: 'Photo or Computer graphics: The survey evaluation'
author: oweissbarth
date: 2019-01-16T21:44:43+00:00
url: /photo-or-computer-graphics-the-survey-evaluation/
featured_image: /images/articles/cg-survey/survey_feature.jpg


---
In the past decade computer graphics have reached a level of realism that makes it hard to distinguish them from actual photos. That is obviously pretty cool. The technological advancements have enabled artists to create amazing artwork and realize their creative vision. We are now as close as never before to visualize anything you can imagine.

However truly photo-realistic cg images also come with some risks. If you can&#8217;t tell a photo from a cg image that opens the door for all kinds of forgery and manipulation.

As part of my studies I am doing a project on “distinguishing between photos and computer graphics using neural networks”. I am building and training a machine learning model to classify input images as either photo or computer graphics. To evaluate the results in a meaningful way I needed something to compare against. Therefore i conducted a small study asking people to classify a selection of 49 photos and computer graphics images. The cg images were collected from {{< new_tab "https://artstation.com" "Artstation.com" >}} while photos were found on {{< new_tab "https://pixabay.com" "Pixabay.com" >}}. I also collected some information about the participants&#8217; background.

To reach a wider audience I used the opportunity to quickly present during the open-stage session at Blender Conference 2018. I described my project and asked for participation in the survey.  


The study is now over and here are the results:

In total I got 2359 responses. The following is my evaluation of the survey. At the bottom of the page you can find links to the raw data licensed under ODC-BY, the evaluation scripts I used as well as the custom survey software.  


# How often do you use 3D-graphics-software (Blender, UE4, Modo, ZBrush, etc&#8230;)?

Possible answers were: Never, Once a month, &nbsp;Once a week, Multiple times a week, Everyday.

The results show that the participants that have never used 3D-graphics-software are almost as well represented as users of 3D-graphics-software. This allows meaningful analysis of both groups.
{{< rawhtml >}}
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.7.3/Chart.bundle.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/chartjs-plugin-datalabels@0.5.0"></script>
<style>
.chartwrapper{
	height: 400px;
	position: relative;
	padding-bottom: 3em;
        margin: 0;
}
</style>



<figure class="chartwrapper">
<canvas id="software"></canvas>
<figcaption><b>Figure 1: </b>Time spent using 3D-graphics-software per week</figcaption>
</figure>

<script type="text/javascript">
	var colors = [
		"#35B26C",
		"#FFA348",
		"#FCFF69",
		"#B24043",
		"#49ABFF"
	]

</script>

<script>
	var labels = ['Never', 'Once a month', 'Once a week', 'Multiple times a week', 'Everyday']
	var data =[1046, 378, 176, 384, 362]
	var datasets = [{
		"data": data,
		"backgroundColor": colors
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('software').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'pie',
	    data: data,
	    options: {
	    	plugins:{
	    		datalabels:{
	    			font:{
	    				size: 22
	    			},
	    			color: ["#383838", "#383838", "#383838", "#FFF", "#FFF"],
					formatter: (value, ctx) => {

		              let sum = 0;
		              let dataArr = ctx.chart.data.datasets[0].data;
		              dataArr.map(data => {
		                  sum += data;
		              });
		              let percentage = (value*100 / sum).toFixed(2)+"%";
		              return percentage;
            		}
            	}
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false
	    }
	});
</script>
{{< /rawhtml >}}

# How much time do you spend per week playing computer/console games?

Possible answers were: less than 1h, 1-3h, 3-6h, 6-12h, more than 12h

Again participants that play many and few games are well represented.  
{{< rawhtml >}}
<figure class="chartwrapper">
<canvas id="video_games"></canvas>
 <figcaption><b>Figure 2: </b>Time spent playing video games per week</figcaption>
</figure>

<script type="text/javascript">
	var colors = [
		"#35B26C",
		"#FFA348",
		"#FCFF69",
		"#B24043",
		"#49ABFF"
	]

</script>

<script>
	var labels = ['less then 1h', '1-3h', '3-6h', '6-12h', 'more than 12h']
	var data =[932, 379, 376, 327, 319]
	var datasets = [{
		"data": data,
		"backgroundColor": colors
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('video_games').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'pie',
	    data: data,
	    options: {
	    	plugins:{
	    		datalabels:{
	    			font:{
	    				size: 22
	    			},
	    			color: ["#383838", "#383838", "#383838", "#FFF", "#FFF"],
					formatter: (value, ctx) => {

		              let sum = 0;
		              let dataArr = ctx.chart.data.datasets[0].data;
		              dataArr.map(data => {
		                  sum += data;
		              });
		              let percentage = (value*100 / sum).toFixed(2)+"%";
		              return percentage;
            		}
            	}
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false
	    }
	});
</script>
{{< /rawhtml >}}

# The interesting part

After those general questions the main part of the survey began. Each image was shown individually in a random order. Once the participant selected the category (cg or photo) the next image was shown. No results were shown in between to not influence the decision based on past results. A “back”-button was not provided.

The following shows each image, the correct label and the percentage of participants that classified it correctly. You can click on the images to enlarge them.
{{< cg_survey_container >}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/morocco-3766064_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/morocco-essaouira-door-window-3766064" accuracy="95.33%"  author="olafpictures" title="Morocco door">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/tomasz-zero-c007-studio-frontside.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/xE3VO" accuracy="87.94%"  author="Tomasz Żero" title="Mercedes-AMG S63">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/christian-ledbetter-nonmarked-6.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/zEWb2" accuracy="82.26%"  author="Christian Ledbetter" title="Reaching for petals">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/IMG_4137.jpg" correctlabel=photo  accuracy="81.26%"  author="Oliver Weissbarth" title="Lake in the city">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/coffee-2242213_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/coffee-cafe-table-drink-work-2242243" accuracy="80.14%"  author="Engin_Akyurt" title="Coffee Table">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/IMG_2690.jpg" correctlabel=photo  accuracy="79.79%"  author="Oliver Weissbarth" title="Sunflowers in the afternoon">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/coffee-beans-3418308_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/ene/coffee-beans-caffeine-coffee-3418308" accuracy="77.56%"  author="Alexas_Fotos" title="Coffee Beans">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/ice-1786311_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/ice-berries-chocolate-ice-dessert-1786311" accuracy="77.55%"  author="Einladung_zum_Essen" title="ice dessert">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/architecture-3588171_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/architecture-glass-modern-city-3588171" accuracy="77.49%"  author="Michael Gaida" title="Architecture Glass">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/tomasz-zero-c001-beauty.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/Q1rd3" accuracy="77.42%"  author="Tomasz Żero" title="Jędrusik">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/IMG_2821.jpg" correctlabel=photo  accuracy="77.21%"  author="Oliver Weissbarth" title="Clouds">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/IMG_2678.jpg" correctlabel=photo  accuracy="76.92%"  author="Oliver Weissbarth" title="On the edge of the road">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/uj01_s.jpg" correctlabel=cg sourceurl="http://www.one2.com.pl" accuracy="75.41%"  author="Krzysztof Pysz ONE2" title="Lennox Residence designed by Artau Architecture">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/cristina-summa-attico-firma.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/1AGD2" accuracy="73.77%"  author="Cristina Summa" title="Black and white Penthouse">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/beautiful-3179182_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/beautiful-asian-woman-japanese-3179182" accuracy="73.7%"  author="khiemmoshe" title="Beautiful asian woman">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/ivo-schoenmakers-new3-1-200.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/Q4vo8" accuracy="72.61%"  author="Ivo Schoenmakers" title="Sitting corner">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/alec-hunstx-midterm-finalrender.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/m9xQZ" accuracy="72.46%"  author="Alec Hunstad" title="Abandoned Clinic">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/nicolas-delille-ladybug-visuel02-cr.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/AdGz" accuracy="72.27%"  author="Nicolas Delille" title="Ladybug Journey - Visual 2">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/deniz-atli-secret-house-1-1.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/DRqlA" accuracy="72.25%"  author="Deniz Atli" title="Forest House">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/enrico-cerica-cuisine23.jpg" correctlabel=cg sourceurl="https://www.myline.be/index.php/en/category/61-industrial-loft-with-scandinavian-style" accuracy="71.83%"  author="Enrico Cerica" title="Industrial loft with scandinavian style">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/headphones-3683983_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/headphones-radio-wireless-headphones-3683983" accuracy="71.62%"  author="HOerwin56" title="Wireless headphones">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/dennis-n-34355e64745079-5adcd0eed0c6a.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/xzA23E" accuracy="67.07%"  author="DennisN / A33SOME CGI Studio" title="Notting Hill Westbourne Grove Apartment">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/andrew-finch-control-pannel.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/v4lz6" accuracy="63.19%"  author="Andrew Finch" title="Control Panel">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/piano-3505109_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/piano-keys-classical-music-3505109" accuracy="62.75%"  author="MabelAmber" title="Piano">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/model-1209985_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/model-girl-woman-portrait-1209985" accuracy="61.66%"  author="ivanovgood" title="Model Girl">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/road-3186188_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/road-highway-travel-asphalt-sky-3186188" accuracy="60.98%"  author="jodeng" title="Road">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/tuna-unalan-raspberry-madness-01.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/03WYe" accuracy="59.68%"  author="Tuna Unalan" title="Raspberry Madness">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/1773.jpg" correctlabel=cg sourceurl="https://www.myline.be/index.php/en/category/64-green-houses-2018" accuracy="59.06%"  author="Enrico Cerica" title="Green House 2018">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/kitchen-2165756_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/kitchen-home-interior-modern-room-2165756" accuracy="59.06%"  author="Skitterphoto" title="Modern Kitchen">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/tomato-2282101_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/tomato-vegetable-food-fresh-red-2282101" accuracy="58.34%"  author="monicore" title="Tomato">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/29823282467_5d838fc41f_h.jpg" correctlabel=cg sourceurl="http://bertrand-benoit.com/blog/classical/" accuracy="57.55%"  author="Bertrand Benoit" title="Classical">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/bottle-caps-1866945_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/bottle-caps-beer-bottles-beer-1866945" accuracy="57.07%"  author="Pexels" title="Bottle caps beer">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/bedroom-1078887_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/bedroom-furniture-chair-dresser-1078887" accuracy="56.87%"  author="Erika Wittlieb" title="Bedroom furniture">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/woman-3584435_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/woman-girl-portrait-beauty-hair-3588435" accuracy="56.51%"  author="JerzyGorecki" title="Woman">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/kitchen-2565105_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/kitchen-interior-design-room-dining-2565105" accuracy="53.58%"  author="StockSnap" title="Kitchen interior">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/marko-ivanovic-final169.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/x6Wr" accuracy="52.88%"  author="Marko Ivanovic" title="Heeeeeere's Johnny!">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/ivo-schoenmakers-handd.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/ZXbvN" accuracy="52.82%"  author="Ivo Schoenmakers" title="Towel Photorealism">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/telescope-2127704_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/telescope-by-looking-view-optics-2127704" accuracy="50.77%"  author="Lars_Nissen_Photoart" title="Telescope">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/IMG_5274.jpg" correctlabel=photo  accuracy="49.06%"  author="Oliver Weissbarth" title="The kings head">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/tomasz-zero-c003-beauty.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/Q1rd3" accuracy="46.96%"  author="Tomasz Żero" title="Jędrusik">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/eoin-o-broin-forest02.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/g5zwG" accuracy="46.94%"  author="Eoin O'Broin" title="UE4 Scenes">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/WC_1024.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/goXe" accuracy="46.04%"  author="Juan Siquier" title="WC">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/36962028523_c565e6cde8_h.jpg" correctlabel=cg sourceurl="http://bertrand-benoit.com/blog/hooper/" accuracy="44.12%"  author="Bertrand Benoit" title="Hooper">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/29823284287_3b6b50da12_h.jpg" correctlabel=cg sourceurl="http://bertrand-benoit.com/blog/classical/" accuracy="43.93%"  author="Bertrand Benoit" title="Classical">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/36922536624_1267ff6ffc_h.jpg" correctlabel=cg sourceurl="http://bertrand-benoit.com/blog/hooper/" accuracy="40.14%"  author="Bertrand Benoit" title="Hooper">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/eoin-o-broin-eoin-o-broin-screenshot00178.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/g5zwG" accuracy="37.11%"  author="Eoin O'Broin" title="UE4 Scenes">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/e-guitar-1736291_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/e-guitar-instrument-music-1736291" accuracy="30.46%"  author="obBilder" title="E guitar">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/glass-565914_1920.jpg" correctlabel=photo sourceurl="http://pixabay.com/en/glass-bottle-wine-glass-transparent-565914" accuracy="29.16%"  author="Yummymoon" title="Glass and Bottle">}}
{{< cg_survey_item imageurl="/images/articles/cg-survey/trevor-curtis-mxsolid-pc-top.jpg" correctlabel=cg sourceurl="https://www.artstation.com/artwork/rG4YL" accuracy="25.83%"  author="Trevor Curtis" title="MxSS Keyboard renders">}}
{{< /cg_survey_container >}}


Overall 62.40% of the images were classified correctly. The participant with the best result classified 100% of the images correctly while the minimum was 26.53%. As 25 out of the 49 images are cg images the expected result with random guessing is 50%. Figure 3 shows a histogram of the accuracy over all participants.

{{< rawhtml >}}
<figure class="chartwrapper">
<canvas id="histogram"></canvas>
<figcaption><b>Figure 3: </b> A histogram over the accuracy of all participants</figcaption>
</figure>
<script type="text/javascript">
	var colors = [
		"#35B26C",
		"#FFA348",
		"#FCFF69",
		"#B24043",
		"#49ABFF",
		"#35B26C",
		"#FFA348",
		"#FCFF69",
		"#B24043",
		"#49ABFF"
	]

</script>

<script>
	var labels = ['26.53-33.88', '33.88-41.22', '41.22-48.57', '48.57-55.92', '55.92-63.27', '63.27-70.61', '70.61-77.96', '77.96-85.31', '85.31-92.65', '92.65-100.00']
	var data =[4, 27, 140, 511, 526, 612, 371, 118, 35, 5]
	var datasets = [{
		"data": data,
		"backgroundColor": colors
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	function fontinfo(context){
		var width = context.chart.width;
  		var size = Math.round(width / 64);
  		if( width > 900){
  			return {
      		size: size,
      		weight: 600
    		};
  		}else{
  			return {
      		size: size*2,
      		weight: 600
    		};
  		}
    	
	}
	function labelrotation(context){
		var width = context.chart.width;
		if(width > 900){
			return 0;
		}else{
			return 90;
		}
	}
	function labelanchor(context){
		var width = context.chart.width;
		if(width > 900){
			return "center";
		}else{
			return "end";
		}
	}
	function labelalign(context){
		var width = context.chart.width;
		if(width > 900){
			return "center";
		}else{
			return "end";
		}
	}
	function labelcolor(context){
		var width = context.chart.width;
		if(width > 900){
			return ["#383838", "#383838", "#383838", "#FFF", "#FFF", "#383838", "#383838", "#383838", "#FFF", "#FFF"];
		}else{
			return "#383838";
		}
	}
	function labelShadow(context){
		var width = context.chart.width;
		if(width > 900){
			return [0, 0 , 0, 5, 5, 0, 0, 0, 5, 5];
		}else{
			return 0;
		}
	}
	var ctx = document.getElementById('histogram').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'bar',
	    data: data,
	    options: {
	    	plugins:{
	    		datalabels:{
	    			font:fontinfo,
	    			rotation: labelrotation,
	    			anchor: labelanchor,
	    			align: labelalign,

	    			textShadowColor: "#000",
	    			textShadowBlur: labelShadow,
	    			color: labelcolor,
					formatter: (value, ctx) => {

		              let sum = 0;
		              let dataArr = ctx.chart.data.datasets[0].data;
		              dataArr.map(data => {
		                  sum += data;
		              });
		              let percentage = (value*100 / sum).toFixed(2)+"%";
		              return value;
            		}
            	}
	    	},
	    	legend:{
	    		display: false
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false,
	    	scales:{
	    		xAxes:[{
	    			ticks: {
                    	autoSkip: false
                	}
	    		}],
	    		yAxes:[
	    			{
	    				ticks: {
                    		max: 900
                		}
	    			}
	    		]
	    	},
	    }
	});
	
</script>
{{< /rawhtml >}}

Figure 4 shows the accuracy based on the time spent using 3D-graphics software. It can be seen that people who use 3D-graphics software on a daily basis classified the images about 8% more accurately than people who have never used 3D-graphics software. This might suggests that the ability to distinguish between photos and cg images is to some extent learnable.
{{< rawhtml >}}
<figure class="chartwrapper">
<canvas id="accuracy_software"></canvas>
<figcaption><b>Figure 4: </b>Average accuracy by 3d-graphics-software usage </figcaption>
</figure>

<script type="text/javascript">
	

</script>

<script>
	var labels = ['Never', 'Once a month', 'Once a week', 'Multiple times a week', 'Everyday']
	var data =[58.66518294896062, 63.022062552826476, 65.03090115276709, 66.6300779699501, 66.92917697856615]
	var xy = data.map((e, i)=> ({"x":i , "y":e} ))
	var datasets = [{
		"data": data,
		"backgroundColor": 		"#FFA348",
		showLine: false,
	    fill: false,
	    pointRadius: 7
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('accuracy_software').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'line',
	    data: data,
	    options: {
	    	legend:{
	    		display: false
	    	},
	    	plugins:{
	    		datalabels:{
	    			display: false
	    		}
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false,
	    	scales:{
	    		xAxes:[{
	    			ticks: {
                    	autoSkip: false
                	}
	    		}]
	    	},
	    },
	});
</script>
{{< /rawhtml >}}

Plotting the accuracy based on the time spent playing video games does not show an obvious correlation (Figure 5).  
{{< rawhtml >}}
<figure class="chartwrapper">
<canvas id="accuracy_games"></canvas>
<figcaption><b>Figure 5: </b>Average accuracy by video game consumption</figcaption>
</figure>

<script type="text/javascript">
	

</script>

<script>
	var labels = ['less then 1h', '1-3h', '3-6h', '6-12h', 'more than 12h']
	var data =[61.766112737925376, 62.98459236366876, 63.295728722965684, 63.15791634923233, 62.18033502476406]
	var xy = data.map((e, i)=> ({"x":i , "y":e} ))
	var datasets = [{
		"data": data,
		"backgroundColor": 		"#FFA348",
		showLine: false,
	    fill: false,
	    pointRadius: 7
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('accuracy_games').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'line',
	    data: data,
	    options: {
	    	legend:{
	    		display: false
	    	},
	    	plugins:{
	    		datalabels:{
	    			display: false
	    		}
	    	
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false,
	    	scales:{
	    		xAxes:[{
	    			ticks: {
                    	autoSkip: false
                	}
	    		}]
	    	},

	    },
	});
</script>
{{< /rawhtml >}}

Another interesting evaluation is to see if participants tend to wrongly classify cg as photo or photo as cg. Figure 6 shows the classification accuracy separately for photo and cg images.

{{< rawhtml >}}
<figure class="chartwrapper chartwrapper-headline">
<div class="sidebyside">
	<h3>CG</h3>
	<canvas id="accuracy_cg"></canvas>
</div>
<div class="sidebyside">
	<h3>photo</h3>
	<canvas id="accuracy_photo"></canvas>
</div>
<figcaption><b>Figure 6: </b>Accuracy per class</figcaption>
</figure>


<script type="text/javascript">
	var colors = [
		"#35B26C",
		"#B24043",
		"#49ABFF"
	]

</script>

<script>
	var labels = ['correct', 'incorrect']
	var data =[60.09739477578553, 39.90260522421447]
	var datasets = [{
		"data": data,
		"backgroundColor": colors
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('accuracy_cg').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'pie',
	    data: data,
	    options: {
	    	plugins:{
	    		datalabels:{
	    			font:{
	    				size: 22
	    			},
	    			color: ["#383838", "#FFF"],
					formatter: (value, ctx) => {

		              let sum = 0;
		              let dataArr = ctx.chart.data.datasets[0].data;
		              dataArr.map(data => {
		                  sum += data;
		              });
		              let percentage = (value*100 / sum).toFixed(2)+"%";
		              return percentage;
            		}
            	}
	    	},
	    	responsive: true,	    	
	    	maintainAspectRatio: false

	    }
	});
	var labels = ['correct', 'incorrect']
	var data =[64.77954930079272, 35.22045069920728]
	var datasets = [{
		"data": data,
		"backgroundColor": colors
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('accuracy_photo').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'pie',
	    data: data,
	    options: {
	    	plugins:{
	    		datalabels:{
	    			font:{
	    				size: 22
	    			},
	    			color: ["#383838", "#FFF"],
					formatter: (value, ctx) => {

		              let sum = 0;
		              let dataArr = ctx.chart.data.datasets[0].data;
		              dataArr.map(data => {
		                  sum += data;
		              });
		              let percentage = (value*100 / sum).toFixed(2)+"%";
		              return percentage;
            		}
            	}
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false

	    }
	});
</script>
<style>
	.sidebyside{
		display: inline-block;
		width: 49%;
		max-height: 400px;
		position: relative;
		padding-bottom: 3em;

	}
	.sidebyside > h3{
		text-align: center;
	}
	.chartwrapper-headline{
		padding-bottom: 6em;
	}
</style>

{{< /rawhtml >}}

It can be seen that participants were slightly better at classifying the photos but not by a significant margin.  


For each image the time it took to decide was also stored. As the survey was not done in a controlled environment these results should be taken with a grain of salt.

That said Figure 7 shows the accuracy based on the average time spent per image. The chart is limited to 120s. All higher values have been cut off. It can be seen that neither deciding instantly nor taken too long yields better results.

{{< rawhtml >}}

<figure class="chartwrapper">
<canvas id="accuracy_time"></canvas>
<figcpation><b>Figure 7: </b>Time spent averaged over all images for each participant</figcpation>
</figure>


<script type="text/javascript">
	var colors = [
		"#35B26C",
		"#B24043",
		"#49ABFF"
	]

</script>

<script>
	var labels = [53.6065918367347, 102.0888163265306, 135.38983673469383, 7.433714285714284, 6.468448979591835, 12.851673469387755, 14.5963, 6.17236, 5.175020000000001, 4.803520000000001, 6.412960000000001, 6.4065400000000015, 8.105859999999998, 6.83664, 4.758519999999999, 8.74116, 9.704280000000004, 9.482160000000002, 9.2774, 10.31964, 6.905859999999999, 13.081280000000001, 14.864859999999997, 3.4660000000000006, 4.47134, 5.824740000000002, 8.243899999999998, 5.419440000000003, 4.09062, 26.368299999999998, 8.726700000000001, 12.457619999999997, 10.910460000000002, 5.416900000000001, 21.838980000000006, 16.521960000000004, 5.8306000000000004, 20.538660000000004, 12.337379999999996, 5.565760000000001, 34.3276, 2.92314, 6.01628, 22.416580000000003, 4.96354, 4.010580000000001, 4.93198, 5.026020000000001, 5.516180000000002, 7.668060000000001, 6.7525400000000015, 14.329519999999997, 3.614819999999999, 9.24164, 10.478399999999999, 31.263459999999995, 8.205739999999999, 7.191060000000001, 12.997939999999998, 10.38124, 13.31562, 20.71324, 4.58838, 3.828020000000001, 5.864539999999998, 22.091279999999998, 5.240660000000002, 4.833279999999999, 6.691819999999996, 5.61354, 5.083300000000001, 3.821459999999999, 7.969999999999999, 8.59124, 12.300540000000002, 3.827640000000001, 5.919859999999999, 8.405820000000002, 10.25806, 4.87448, 39.272359999999985, 3.28684, 4.03202, 5.692300000000001, 10.556860000000004, 2.7725999999999993, 6.98464, 8.052, 12.261400000000002, 6.0911599999999995, 6.459160000000001, 4.94268, 12.458280000000002, 12.88734, 5.638959999999998, 15.03362, 7.7594, 13.028739999999997, 36.3976, 80.43256, 10.336259999999998, 10.076459999999999, 9.551819999999998, 4.16012, 4.012880000000001, 8.64656, 8.015540000000001, 14.083579999999998, 78.37512, 8.62192, 6.651620000000003, 92.95892000000003, 12.038639999999997, 3.9219000000000004, 13.908499999999998, 3.362039999999999, 6.07476, 6.672280000000003, 4.108419999999999, 4.004839999999999, 4.492739999999999, 138.18682, 4.426519999999999, 8.704320000000001, 7.799059999999997, 19.786099999999998, 199.51734, 6.093460000000001, 19.20676, 74.92998, 5.1936599999999995, 7.917679999999999, 9.081760000000003, 8.577499999999999, 14.03136, 29.62666, 7.041960000000001, 6.471180000000001, 23.711519999999997, 215.06376, 12.714260000000001, 21.85488, 3.12134, 8.970300000000002, 6.880019999999999, 4.742239999999998, 9.472879999999998, 5.290740000000002, 9.439580000000001, 14.157659999999998, 15.454200000000005, 31.15026, 16.479799999999997, 2.1979200000000008, 5.1538, 3.1212999999999997, 21.951359999999994, 11.583979999999999, 6.780080000000002, 3.6045400000000005, 3.707760000000001, 8.260840000000002, 4.69652, 12.734200000000001, 35.011079999999986, 61.70442000000002, 62.278519999999986, 7.80586, 18.10624, 3.29674, 6.232140000000002, 4.201839999999999, 3.9512199999999997, 1.8108799999999996, 4.9361, 3.5771599999999997, 11.178840000000003, 8.017919999999998, 4.10922, 8.897240000000002, 8.086319999999999, 69.74670000000003, 14.30954, 18.222600000000003, 16.140600000000003, 4.83118, 2.0018599999999993, 4.384759999999999, 3.9677199999999995, 6.268519999999998, 10.413980000000002, 7.039739999999999, 6.447780000000002, 2.2662999999999998, 20.085699999999996, 4.934520000000001, 17.19238, 21.826020000000003, 3.13398, 5.52338, 7.39222, 2.75628, 9.627659999999999, 37.62536000000001, 22.75782000000001, 5.103899999999999, 22.15750000000001, 5.763020000000001, 2.6066599999999998, 5.031, 10.831840000000001, 5.5339599999999995, 9.41196, 2.4146600000000005, 6.116239999999998, 6.345420000000001, 10.022060000000003, 4.7693200000000004, 5.594540000000002, 19.382760000000005, 5.55692, 10.14252, 3.9337, 5.80584, 31.181880000000007, 6.478419999999999, 9.250580000000001, 6.391600000000002, 0.22546000000000008, 3.0517200000000004, 5.50778, 7.731699999999997, 34.59888000000001, 6.13966, 25.343260000000008, 2.91026, 21.471439999999998, 5.656479999999999, 7.61588, 6.757179999999998, 7.214880000000001, 6.49456, 2.988259999999999, 4.3585199999999995, 4.91324, 4.085840000000001, 3.4758200000000006, 2.0686200000000006, 3.8290800000000003, 54.40995999999999, 4.681979999999999, 14.072460000000003, 6.9999199999999995, 5.453860000000001, 9.558060000000001, 14.543520000000001, 5.588479999999999, 4.3618, 35.26102, 110.59978000000002, 3.8961200000000002, 20.667559999999998, 6.457919999999999, 18.27278, 7.2162000000000015, 2.0111600000000003, 5.1250800000000005, 5.301699999999999, 6.1243, 10.587939999999996, 5.169139999999999, 4.27394, 9.437199999999997, 6.166200000000001, 6.961860000000001, 7.77578, 7.812220000000001, 7.689459999999998, 73.92124, 8.01256, 14.783680000000002, 5.736439999999999, 3.4949399999999984, 3.4396, 16.6224, 4.296679999999999, 14.740299999999998, 5.4769, 10.31182, 4.90416, 7.83066, 4.51596, 4.553199999999999, 5.286000000000002, 12.333280000000002, 7.5797000000000025, 3.731780000000001, 5.846099999999999, 14.019420000000004, 6.873480000000002, 16.254759999999997, 0.56614, 6.80812, 7.21724, 10.105820000000001, 4.33642, 80.24201999999998, 44.83873999999999, 9.86148, 3.07662, 2.6445399999999997, 71.4178, 3.2358800000000003, 3.8024600000000004, 6.623699999999999, 5.827139999999998, 3.61952, 3.59, 14.759859999999993, 10.48268, 10.588299999999998, 18.57302, 9.692280000000002, 25.68352, 4.46806, 9.05542, 4.490939999999999, 5.702560000000001, 6.72402, 3.4152599999999995, 4.221219999999999, 10.10944, 20.1423, 13.398420000000005, 4.91464, 65.09728, 15.2653, 13.45536, 15.90674, 5.084379999999999, 69.17432000000001, 5.4489, 10.519999999999996, 4.794319999999998, 7.787920000000001, 12.24106, 9.488359999999998, 4.74564, 2.8334200000000016, 3.3093199999999996, 17.634840000000008, 10.02276, 4.973539999999999, 5.705159999999999, 3.7925999999999997, 6.685600000000001, 6.121839999999999, 2.64764, 9.623080000000002, 5.44118, 3.217899999999999, 17.843500000000002, 3.8260399999999994, 12.883679999999996, 8.864600000000001, 2.7790599999999994, 3.008840000000001, 4.399580000000001, 13.499380000000004, 3.9599800000000003, 5.032840000000002, 4.4889600000000005, 7.44904, 11.54086, 24.184740000000005, 4.27594, 1.6923599999999999, 55.23692, 3.4229000000000007, 5.324759999999999, 2.0802600000000004, 17.515980000000003, 3.8096400000000004, 9.631600000000002, 6.272440000000002, 10.569379999999999, 3.9113599999999997, 10.12158, 4.80454, 4.999019999999999, 3.5239599999999998, 6.1139600000000005, 4.3962200000000005, 6.6199200000000005, 5.4648200000000005, 10.054740000000002, 3.695420000000001, 2.2127399999999997, 7.0636199999999985, 2.5644400000000003, 4.36992, 3.7634, 5.482440000000002, 6.630880000000001, 2.960999999999999, 5.75128, 3.45908, 0.24231999999999998, 3.3394000000000004, 9.7917, 4.5582400000000005, 3.677439999999999, 14.516359999999997, 8.054920000000001, 8.433639999999999, 6.368560000000001, 3.8534599999999997, 13.118719999999998, 3.65778, 5.98764, 3.5880199999999998, 27.655119999999997, 22.13102, 8.70504, 5.135840000000001, 6.377759999999999, 7.990519999999999, 32.91814, 6.395420000000001, 7.1284399999999986, 4.880800000000001, 5.660999999999999, 21.849019999999996, 7.847759999999998, 11.20838, 8.571900000000001, 7.1296800000000005, 16.972119999999997, 2.5128200000000005, 7.976719999999998, 4.849, 6.06094, 34.111079999999994, 3.3156600000000007, 3.978660000000001, 3.833979999999999, 4.9279, 10.158299999999999, 7.07392, 7.145180000000002, 6.395639999999998, 5.933679999999999, 0.30767999999999995, 3.15952, 4.756119999999998, 7.724459999999999, 6.6522799999999975, 6.4173599999999995, 11.760459999999998, 14.37474, 4.117740000000001, 5.7161, 14.683840000000005, 8.27342, 3.5487999999999995, 6.2213400000000005, 5.708660000000001, 7.5838600000000005, 7.536199999999996, 3.6683200000000005, 9.00112, 17.425939999999997, 3.0862799999999995, 49.374520000000004, 3.9062799999999998, 7.400719999999998, 4.607679999999999, 5.394939999999998, 3.6745199999999993, 5.612680000000004, 2.95284, 10.076160000000002, 3.182339999999999, 12.316339999999995, 17.872519999999998, 3.3585399999999996, 9.84376, 3.204439999999999, 5.310319999999999, 9.08942, 6.053340000000002, 3.51148, 4.26754, 2.8181, 3.05726, 15.98686, 3.6024999999999987, 37.66782, 5.394679999999999, 19.806520000000003, 6.773639999999999, 0.9436999999999998, 5.28638, 5.6525599999999985, 3.5359799999999995, 70.37759999999999, 2.722060000000001, 4.977199999999999, 10.161980000000002, 66.43523999999998, 40.986279999999994, 7.108520000000002, 18.832959999999993, 0.7379599999999997, 3.825619999999999, 3.5089599999999996, 9.499020000000005, 3.85826, 6.6869000000000005, 3.2024199999999996, 3.0586399999999996, 4.7495199999999995, 8.26916, 25.57182, 7.433340000000002, 5.21844, 5.776979999999998, 5.661740000000001, 17.6188, 4.196879999999999, 6.712479999999999, 4.8216399999999995, 4.97372, 3.2401400000000002, 10.296440000000002, 21.149219999999996, 4.85772, 15.986299999999996, 3.7574200000000015, 3.7333599999999993, 6.4398, 7.305860000000001, 3.6933999999999996, 8.087, 3.985139999999999, 4.766299999999998, 3.5872999999999995, 5.62276, 9.479180000000001, 4.96544, 6.189920000000002, 4.7713600000000005, 3.3145600000000015, 11.131160000000001, 4.854520000000001, 6.980719999999998, 2.173459999999999, 9.316799999999999, 3.50116, 5.210420000000002, 19.39178, 5.59328, 4.638560000000002, 4.6410399999999985, 5.29188, 13.053540000000003, 5.384459999999999, 24.55311999999999, 4.760720000000001, 5.516460000000002, 8.77152, 3.4280400000000015, 3.346260000000001, 6.581179999999998, 6.73954, 5.534760000000001, 3.3096000000000005, 13.274720000000004, 7.118439999999998, 6.89172, 3.030299999999999, 10.9082, 9.5925, 11.829520000000004, 6.211239999999998, 3.953819999999999, 3.2670400000000006, 5.990879999999999, 3.0635399999999993, 3.531600000000001, 11.598000000000003, 4.297279999999998, 24.33836, 5.169599999999999, 17.58904, 17.120780000000003, 3.0526000000000004, 20.733159999999998, 5.9291800000000014, 8.40518, 4.8453800000000005, 4.218120000000001, 6.4295800000000005, 6.327459999999999, 6.6454200000000005, 5.5569000000000015, 5.88292, 2.7628200000000005, 17.494319999999995, 1.8985799999999995, 20.468600000000002, 11.580279999999998, 5.658420000000001, 10.441080000000001, 29.51056000000001, 9.781979999999999, 17.385899999999996, 6.693660000000002, 5.676440000000001, 4.77512, 6.278, 3.73966, 4.519759999999999, 11.751900000000001, 27.760240000000003, 16.41399999999999, 3.93966, 5.6051400000000005, 34.768000000000015, 10.21968, 4.4619800000000005, 17.836959999999998, 4.04746, 3.909200000000001, 7.795639999999999, 4.74268, 11.14358, 18.30352, 95.15114000000001, 5.43962, 14.4251, 7.08532, 16.287739999999996, 6.570540000000001, 5.526700000000001, 6.503539999999998, 5.70138, 6.5382200000000035, 8.70824, 7.750359999999998, 15.90502, 3.597019999999999, 16.232680000000002, 3.778, 31.31946, 10.615699999999997, 28.75438, 1.1649199999999995, 17.915240000000008, 5.6326800000000015, 11.780920000000002, 7.593279999999998, 6.022220000000001, 27.822740000000003, 5.621900000000002, 9.424900000000001, 44.28274, 5.302019999999999, 5.23572, 5.231940000000001, 3.4605599999999996, 6.11954, 7.295900000000002, 17.002799999999993, 12.50144, 5.223599999999998, 3.709079999999999, 7.723539999999999, 8.396, 23.207740000000005, 1.9118799999999998, 4.029259999999999, 6.15084, 6.6270799999999985, 6.414240000000001, 14.003340000000001, 19.943520000000007, 2.5877000000000003, 7.745500000000004, 4.411219999999998, 41.331800000000015, 9.685199999999998, 2.0678400000000003, 5.033399999999999, 10.894379999999998, 28.179560000000002, 5.0845400000000005, 4.4032800000000005, 6.922719999999997, 6.5449600000000006, 84.774, 9.487500000000002, 4.43978, 3.0691999999999995, 5.21858, 437.1887799999999, 4.764204081632654, 16.665346938775514, 16.949142857142853, 15.19726530612245, 7.380999999999999, 6.88430612244898, 7.012816326530612, 4.443163265306121, 14.731244897959181, 2.8021020408163264, 3.3806734693877543, 7.787142857142856, 4.637693877551019, 8.250408163265305, 6.571000000000001, 4.707265306122449, 2.8057346938775516, 2.737816326530612, 4.70469387755102, 9.512224489795917, 8.12461224489796, 10.109285714285713, 65.52985714285714, 13.746795918367345, 17.920816326530616, 5.294387755102041, 5.0126122448979595, 3.7432448979591837, 7.88226530612245, 4.704979591836735, 14.63438775510204, 3.7424285714285705, 12.326693877551023, 7.207367346938778, 8.928693877551021, 4.001999999999999, 11.08873469387755, 5.638775510204083, 6.143897959183672, 13.1094693877551, 3.899469387755102, 14.004530612244897, 15.255693877551023, 34.90195918367347, 14.226081632653061, 4.350510204081633, 7.558775510204081, 9.03716326530612, 1.8085714285714283, 4.505755102040816, 7.568938775510205, 18.464346938775513, 26.722122448979587, 10.173510204081634, 1.7558367346938781, 18.6074693877551, 2.453224489795918, 11.93124489795918, 7.8620408163265285, 5.228163265306122, 7.730999999999999, 7.3994081632653055, 3.1966326530612257, 17.25283673469388, 8.069244897959184, 6.110734693877551, 2.421775510204082, 6.972408163265308, 10.222510204081635, 3.3020816326530618, 4.615489795918367, 3.683326530612245, 4.953673469387755, 5.189204081632655, 3.0728979591836723, 16.362469387755105, 2.7769795918367346, 4.2483877551020415, 13.294285714285712, 3.8415102040816325, 4.041551020408165, 26.109061224489793, 4.941510204081632, 4.794122448979592, 3.755693877551021, 3.337102040816326, 6.178530612244899, 7.14457142857143, 19.238142857142854, 4.61091836734694, 22.802714285714284, 42.64932653061226, 3.700448979591836, 404.1544489795919, 5.05304081632653, 3.1682653061224495, 11.323897959183677, 17.71604081632653, 6.210469387755103, 3.25, 6.596571428571428, 4.250387755102041, 9.001979591836738, 3.2387551020408147, 5.799061224489795, 5.290836734693877, 9.237571428571428, 26.266489795918357, 3.6899999999999995, 13.960285714285714, 6.592591836734694, 3.238632653061224, 19.80704081632653, 3.42295918367347, 17.780673469387754, 6.525653061224492, 3.7874897959183658, 9.018836734693878, 17.46369387755102, 8.571040816326532, 9.305979591836735, 8.94095918367347, 8.74077551020408, 13.511367346938776, 5.395734693877551, 6.384489795918368, 5.807183673469388, 7.889183673469386, 10.19395918367347, 18.095306122448978, 3.6199795918367332, 6.214265306122448, 36.90830612244899, 5.8087755102040814, 4.527734693877551, 7.534387755102041, 31.46855102040816, 6.553632653061225, 6.6081836734693855, 7.365020408163263, 5.977469387755101, 6.349775510204082, 28.765040816326533, 11.494224489795918, 5.554857142857142, 2.1119387755102044, 5.691938775510203, 6.926734693877552, 15.525408163265306, 188.51279591836732, 7.192755102040818, 2.831367346938775, 3.605714285714286, 16.74987755102041, 3.7946530612244898, 9.199244897959186, 2.801632653061225, 9.000530612244898, 3.102163265306121, 4.4767755102040825, 7.7728571428571405, 4.367734693877551, 5.6772653061224485, 4.560959183673471, 7.802020408163266, 6.178040816326532, 7.295346938775511, 5.43138775510204, 10.589897959183673, 11.877163265306125, 14.844959183673467, 3.440489795918368, 9.993448979591834, 3.6656734693877544, 9.774938775510202, 20.688081632653063, 7.605448979591837, 3.4156530612244884, 3.9033877551020413, 16.78620408163265, 12.316489795918368, 8.916836734693877, 3.8798163265306123, 6.230612244897959, 5.795714285714286, 2.9255102040816325, 6.43604081632653, 7.971591836734695, 6.052163265306123, 4.38795918367347, 7.255755102040817, 2.9608367346938773, 9.506306122448983, 8.352469387755106, 8.636, 13.283244897959182, 4.977244897959183, 4.1106734693877565, 7.281816326530612, 21.44824489795918, 4.3402040816326535, 2.5030816326530614, 3.47730612244898, 11.118040816326529, 10.13851020408163, 3.264244897959184, 8.63844897959184, 2.4906122448979593, 5.002571428571428, 11.604632653061222, 21.917693877551024, 2.110142857142857, 3.382081632653061, 2.9826530612244895, 6.966918367346938, 2.8480204081632654, 5.759673469387755, 7.563204081632654, 5.376306122448977, 4.4291224489795935, 5.369142857142857, 4.667040816326531, 2.3853265306122444, 7.124734693877551, 5.207755102040817, 6.4378979591836725, 4.352653061224491, 4.109673469387755, 5.932122448979591, 15.560204081632651, 3.8712448979591847, 9.110102040816326, 13.90589795918367, 7.534163265306122, 27.591836734693885, 11.082673469387757, 8.075591836734693, 10.24134693877551, 4.004714285714286, 10.228653061224488, 3.4105306122448993, 5.124918367346938, 4.412244897959184, 11.14479591836735, 4.87277551020408, 6.9219795918367355, 2.3860612244897967, 3.5229387755102026, 5.1630612244897955, 13.468938775510209, 9.360122448979594, 4.061020408163266, 4.927469387755103, 2.808734693877551, 3.0306734693877546, 4.015326530612245, 11.017897959183674, 4.698020408163266, 5.829673469387752, 2.682285714285715, 5.386551020408161, 6.288122448979592, 6.618510204081633, 2.989510204081633, 6.746122448979589, 2.1630816326530615, 8.119591836734696, 9.777897959183674, 3.574081632653061, 11.781408163265306, 3.8047959183673457, 14.397387755102043, 2.2938775510204077, 10.158163265306122, 10.472999999999995, 4.929428571428572, 4.743061224489795, 12.092938775510206, 26.651122448979592, 4.5439591836734685, 10.915285714285712, 6.493673469387757, 6.133224489795916, 7.796918367346939, 9.140020408163263, 5.04261224489796, 5.915326530612245, 2.9444081632653067, 2.4141632653061222, 3.8646122448979594, 8.594000000000003, 2.3648367346938772, 6.935795918367346, 15.330693877551019, 2.478265306122449, 3.370489795918367, 6.53965306122449, 7.577244897959182, 3.944122448979592, 8.335897959183676, 4.163755102040817, 8.389530612244897, 16.78314285714286, 11.406612244897959, 16.16744897959184, 3.336061224489796, 2.9904285714285708, 2.7674081632653063, 4.3710612244897975, 3.5943265306122454, 9.149918367346938, 5.8335306122449, 3.462163265306124, 5.313877551020408, 4.4251632653061215, 6.359673469387754, 4.619877551020409, 5.625510204081632, 6.56895918367347, 13.644999999999994, 2.1414285714285715, 9.161265306122448, 5.925877551020407, 3.8768163265306113, 3.7448775510204073, 13.25361224489796, 6.2964693877551055, 3.3228367346938783, 5.11808163265306, 39.47538775510204, 121.29718367346939, 5.31861224489796, 2.8570204081632653, 2.270612244897959, 25.43918367346938, 54.417122448979576, 3.553326530612245, 8.762489795918366, 2.163979591836735, 166.95514285714285, 7.958591836734694, 31.12522448979591, 6.227285714285714, 5.8147142857142855, 10.384081632653064, 14.521795918367351, 8.021020408163267, 2.3641632653061224, 3.804224489795917, 4.537102040816326, 21.564020408163273, 3.059938775510204, 5.704775510204082, 3.5667142857142857, 6.021224489795919, 1.3507346938775515, 3.3258979591836755, 5.781612244897958, 57.12085714285713, 2.163224489795919, 5.188326530612245, 6.23720408163265, 5.023938775510204, 3.0862448979591837, 8.03310204081633, 2.132102040816326, 4.761020408163264, 3.6970408163265307, 227.49432653061223, 8.031836734693876, 9.80938775510204, 3.810857142857143, 5.176591836734694, 334.22293877551016, 4.3825306122448975, 7.598673469387755, 5.7720204081632644, 9.936714285714286, 11.106734693877549, 5.4829591836734695, 5.265183673469387, 24.088367346938774, 9.117040816326531, 3.824326530612247, 8.622367346938773, 13.10069387755102, 4.452061224489796, 2.9875306122448984, 4.475816326530612, 20.970632653061223, 6.585204081632652, 14.504999999999997, 3.2212040816326524, 4.389816326530612, 6.3301224489795915, 13.491163265306122, 6.09930612244898, 23.46318367346938, 9.614265306122448, 8.511755102040818, 13.729918367346936, 32.332306122448976, 4.469714285714284, 4.810224489795919, 24.14512244897959, 5.328571428571428, 22.6755306122449, 9.546204081632657, 7.89026530612245, 4.518530612244896, 7.3425306122448974, 606.7543673469389, 11.716877551020406, 11.9704081632653, 4.119591836734694, 18.356306122448984, 6.256979591836735, 9.295326530612243, 2.973897959183673, 9.390755102040815, 2.6922040816326533, 4.895040816326531, 2.9943877551020415, 4.855938775510204, 7.374510204081629, 99.21420408163263, 4.967734693877553, 13.427551020408163, 3.592102040816328, 4.240081632653061, 26.55634693877551, 8.749163265306123, 5.277061224489795, 10.114489795918368, 8.745061224489794, 4.771489795918368, 8.544367346938776, 5.790122448979593, 5.550673469387755, 151.87710204081634, 12.906551020408164, 3.8144081632653073, 3.1200204081632648, 6.599448979591837, 1.7704285714285721, 7.334163265306123, 5.118714285714287, 4.820510204081632, 6.4154897959183685, 6.496897959183675, 4.830897959183673, 4.729918367346939, 13.866571428571433, 8.681346938775514, 4.712755102040816, 15.335938775510204, 9.27965306122449, 4.058285714285716, 4.283081632653062, 7.498183673469388, 5.682510204081632, 4.719938775510205, 11.549510204081631, 6.757183673469391, 19.975693877551024, 6.688591836734693, 14.420142857142853, 4.9924897959183685, 3.7692857142857146, 5.53648979591837, 51.43712244897961, 4.74742857142857, 5.4405510204081615, 8.414408163265305, 3.8088163265306116, 5.295836734693879, 5.7202244897959185, 4.261040816326532, 12.533408163265305, 17.143285714285714, 4.158857142857142, 5.704102040816327, 4.773122448979592, 6.449102040816327, 6.163000000000004, 6.11195918367347, 17.46461224489795, 10.880693877551021, 9.41930612244898, 12.044122448979595, 16.70973469387755, 7.224142857142858, 7.450387755102041, 4.606081632653063, 8.265591836734691, 11.137346938775513, 34.729244897959184, 10.055183673469386, 14.470244897959182, 2.767040816326531, 21.918775510204078, 4.184673469387754, 39.10989795918368, 29.71132653061225, 24.038775510204093, 12.478551020408165, 5.81742857142857, 6.263551020408163, 3.487306122448979, 22.610795918367344, 10.975081632653064, 4.056448979591838, 11.497224489795919, 2.491, 7.403102040816326, 8.261938775510203, 7.112795918367348, 13.351755102040821, 7.979469387755103, 2.6627346938775514, 5.553836734693879, 8.997367346938773, 9.251448979591837, 2.5126326530612246, 15.065673469387754, 10.840040816326526, 13.30648979591837, 3.8433673469387766, 16.663204081632657, 11.041836734693877, 11.340897959183673, 5.897979591836736, 4.718816326530611, 16.016836734693875, 3.0693265306122455, 21.187632653061225, 15.607428571428569, 14.697673469387759, 4.939673469387754, 4.528979591836734, 5.882040816326531, 3.454877551020409, 11.460673469387757, 15.508795918367348, 3.5228979591836724, 5.973020408163265, 6.71061224489796, 22.038816326530608, 2.759408163265306, 93.4129591836735, 7.22526530612245, 6.346244897959184, 5.969387755102042, 7.007367346938778, 3.6441632653061227, 4.729204081632654, 6.572877551020411, 3.0168979591836735, 39.88475510204081, 10.168408163265306, 5.811979591836735, 6.602734693877548, 7.274346938775512, 10.120244897959179, 5.299836734693876, 5.443183673469388, 9.62761224489796, 6.342040816326531, 6.584081632653059, 2.930408163265306, 3.938857142857143, 7.0892857142857135, 9.265224489795921, 24.529469387755107, 7.329612244897961, 3.819591836734694, 15.599571428571426, 5.907693877551023, 6.117204081632653, 7.880653061224492, 6.406408163265306, 24.844816326530612, 12.318306122448979, 20.297163265306125, 9.51104081632653, 5.698734693877551, 5.77565306122449, 27.989102040816324, 11.463326530612244, 11.42922448979592, 7.340938775510204, 7.960571428571428, 5.244367346938775, 36.1437142857143, 9.71112244897959, 10.65997959183673, 3.605142857142857, 5.6524693877551035, 12.907224489795915, 13.097142857142854, 6.986693877551019, 5.132326530612246, 8.502061224489797, 3.5441632653061235, 7.135448979591836, 5.796489795918369, 16.821448979591835, 4.463653061224489, 3.3153469387755097, 11.715408163265305, 7.96487755102041, 14.988285714285714, 3.084102040816327, 3.8298571428571435, 13.386632653061225, 2.033816326530613, 6.384918367346938, 6.57542857142857, 4.292632653061223, 4.918489795918368, 11.460020408163263, 5.52065306122449, 51.82163265306125, 10.48385714285714, 6.992653061224489, 9.535224489795922, 11.015714285714285, 4.31961224489796, 6.686367346938774, 3.808020408163265, 12.778775510204083, 60.91738775510203, 6.497857142857144, 14.007306122448979, 7.4503673469387754, 6.304489795918369, 4.882836734693876, 6.186408163265305, 13.535469387755098, 12.88491836734694, 6.083428571428571, 20.001183673469388, 13.99883673469388, 6.937857142857141, 12.878346938775513, 8.704061224489797, 2.829551020408164, 9.141081632653062, 11.13295918367347, 5.72230612244898, 11.361040816326534, 11.159163265306125, 15.992836734693878, 64.53693877551022, 5.6480816326530645, 21.318530612244903, 14.579122448979593, 4.5606530612244915, 1.4802244897959183, 6.272510204081632, 10.310428571428572, 4.606040816326531, 4.870408163265306, 5.699448979591837, 16.072979591836734, 5.511448979591838, 7.585326530612246, 21.97808163265307, 3.766081632653062, 78.29183673469386, 8.984204081632656, 34.43577551020409, 4.776448979591836, 19.595530612244897, 13.199122448979587, 9.194673469387757, 44.03548979591835, 7.653204081632654, 7.042102040816327, 7.556755102040817, 18.384734693877547, 5.16930612244898, 7.3810612244897955, 8.390102040816329, 10.87565306122449, 9.953959183673467, 10.487367346938772, 9.56267346938775, 7.490612244897959, 11.37718367346939, 5.262244897959184, 9.27183673469388, 11.055795918367345, 12.118081632653062, 14.936448979591832, 6.929040816326531, 4.722959183673471, 15.11734693877551, 8.37273469387755, 28.945653061224483, 6.945428571428572, 16.020040816326535, 14.247632653061224, 6.4452857142857125, 21.915346938775507, 10.014755102040816, 18.000510204081632, 13.127877551020404, 11.787938775510199, 6.284346938775511, 11.080244897959187, 11.594877551020408, 9.398020408163266, 20.54463265306122, 12.911102040816331, 12.62257142857143, 8.079959183673468, 17.28920408163265, 7.015755102040816, 3.8509795918367353, 5.676367346938775, 4.500918367346939, 4.930489795918369, 7.893795918367348, 5.815020408163266, 19.0514081632653, 3.6037346938775503, 22.981510204081623, 18.883673469387755, 4.955163265306124, 4.418163265306124, 6.8695306122448985, 11.92173469387755, 6.683224489795919, 3.172469387755102, 19.038367346938777, 8.048428571428573, 5.545755102040818, 12.772571428571425, 4.4829387755102035, 18.8105306122449, 12.802244897959183, 12.459367346938777, 39.31483673469389, 12.011918367346935, 7.141285714285714, 1.533530612244898, 7.106489795918369, 4.94895918367347, 12.526714285714288, 7.950244897959185, 9.636693877551021, 21.577510204081623, 6.220285714285718, 11.357632653061225, 7.243693877551021, 13.63130612244898, 14.466591836734697, 10.904571428571428, 7.855530612244896, 17.408877551020414, 17.672795918367346, 7.69487755102041, 10.609244897959181, 6.635836734693878, 8.418693877551021, 14.376999999999999, 11.20440816326531, 8.777979591836731, 4.637265306122449, 6.498204081632651, 3.644489795918367, 39.45079591836735, 19.87308163265306, 9.357448979591837, 5.278408163265306, 17.776693877551015, 11.132755102040814, 4.901183673469389, 12.15287755102041, 14.661795918367346, 17.832326530612242, 11.429183673469392, 5.098571428571428, 8.250489795918364, 7.326306122448979, 3.4544693877551014, 7.09134693877551, 4.128346938775512, 16.675857142857147, 19.94834693877551, 20.23804081632653, 53.997918367346934, 7.589326530612243, 7.017673469387756, 8.778408163265308, 8.456306122448984, 7.312469387755103, 8.969306122448982, 35.8527551020408, 6.60916326530612, 5.4748775510204055, 5.913714285714285, 5.826489795918366, 17.132918367346935, 7.207346938775511, 3.559244897959183, 4.5354897959183695, 4.453, 10.898326530612243, 10.289897959183676, 4.602510204081632, 4.5576326530612254, 5.938897959183673, 3.530571428571429, 5.737755102040817, 4.0688979591836745, 9.04630612244898, 5.771306122448979, 12.75589795918367, 31.567897959183668, 6.337020408163266, 10.590204081632654, 4.908530612244898, 0.2024285714285715, 8.505142857142856, 2.992081632653063, 9.128408163265307, 5.8155918367346935, 6.113326530612244, 152.99363265306124, 6.902612244897958, 7.335857142857142, 3.3386326530612243, 6.9005918367346935, 8.130551020408163, 4.1230816326530615, 16.63722448979592, 9.131244897959181, 31.355265306122444, 9.199102040816326, 10.92208163265306, 5.116183673469388, 15.737632653061226, 8.569918367346936, 14.531122448979593, 9.25234693877551, 2.6824489795918365, 9.447857142857139, 26.275448979591832, 5.148897959183674, 4.023979591836735, 7.21795918367347, 19.35651020408163, 12.032897959183673, 11.969877551020408, 8.850469387755101, 6.13161224489796, 2.0258775510204083, 12.73457142857143, 20.48577551020408, 9.873346938775512, 6.748551020408163, 6.81769387755102, 10.240918367346941, 10.678653061224495, 4.405326530612244, 5.402244897959185, 11.929530612244898, 16.599285714285713, 9.646285714285716, 8.262816326530617, 6.550020408163266, 6.109816326530612, 6.083591836734694, 8.006081632653064, 11.62122448979592, 4.345244897959184, 19.165714285714287, 41.03073469387756, 22.983285714285714, 5.903102040816327, 22.749204081632655, 8.449714285714286, 4.3745510204081635, 12.045367346938777, 63.46818367346938, 5.932693877551021, 12.013816326530614, 3.7004285714285707, 4.750224489795917, 5.687244897959181, 15.240285714285708, 11.971551020408164, 18.15340816326531, 9.035632653061224, 8.56295918367347, 4.2401428571428585, 8.859163265306123, 4.826673469387755, 27.916448979591834, 12.319306122448976, 8.137204081632653, 42.339000000000006, 11.524653061224484, 4.593510204081634, 5.386428571428569, 3.281367346938776, 10.313795918367347, 11.18508163265306, 84.1598979591837, 13.815551020408158, 4.876163265306124, 8.28773469387755, 9.172346938775506, 15.25930612244898, 3.4534489795918373, 15.763673469387754, 5.6369591836734685, 9.109081632653064, 11.173469387755098, 12.151367346938779, 10.30012244897959, 4.450714285714286, 4.678999999999999, 4.600510204081631, 4.10095918367347, 13.371918367346938, 11.501428571428567, 6.3491428571428585, 17.062285714285714, 12.531836734693876, 43.29302040816327, 6.437163265306122, 12.745224489795921, 6.937142857142854, 15.596632653061224, 12.314346938775511, 7.614367346938775, 26.37818367346939, 4.47426530612245, 10.469795918367346, 4.86191836734694, 7.628693877551021, 14.220959183673465, 21.46926530612245, 14.794959183673466, 4.839877551020407, 6.213551020408162, 4.562571428571427, 8.827387755102038, 7.156979591836736, 7.306795918367348, 7.312857142857142, 19.050183673469395, 15.005244897959178, 11.003122448979592, 6.917673469387753, 5.637836734693878, 13.661551020408162, 5.596897959183676, 10.351857142857142, 12.769265306122449, 27.186836734693877, 9.164979591836733, 15.011530612244895, 5.179183673469388, 17.60640816326531, 6.186897959183675, 13.630387755102044, 5.9331836734693875, 10.630551020408163, 9.556612244897957, 9.128183673469389, 8.013163265306122, 4.045265306122449, 2.67934693877551, 7.603612244897958, 4.336469387755102, 5.823979591836736, 45.593877551020405, 10.342979591836732, 10.170775510204082, 26.78687755102041, 11.877857142857145, 11.36177551020408, 8.872224489795915, 11.645163265306122, 13.653285714285714, 18.74169387755102, 4.010877551020409, 7.817408163265306, 12.217489795918363, 39.69834693877551, 3.6670408163265313, 5.559326530612246, 10.364122448979591, 12.690040816326533, 4.18134693877551, 18.2800612244898, 4.70038775510204, 7.32222448979592, 7.3219183673469415, 6.499591836734695, 5.284653061224487, 22.434306122448973, 7.198020408163266, 12.288510204081629, 10.95518367346939, 8.176081632653062, 4.844836734693876, 12.456877551020412, 17.077061224489803, 6.899510204081632, 21.78051020408163, 18.948346938775508, 11.913224489795917, 14.691571428571434, 12.43738775510204, 5.5418979591836734, 6.792102040816325, 6.081857142857146, 7.3032244897959195, 6.825877551020407, 6.897938775510208, 6.202612244897959, 8.877040816326529, 8.169346938775512, 4.868061224489796, 7.603530612244897, 6.107714285714285, 5.461346938775509, 17.573734693877547, 2.1173265306122446, 26.08351020408162, 6.469448979591838, 10.078775510204084, 7.010489795918368, 8.16426530612245, 249.9714285714286, 9.806755102040816, 30.43634693877551, 4.9408775510204075, 59.70930612244898, 5.092571428571429, 6.091367346938775, 8.022367346938776, 13.71120408163265, 10.641571428571428, 30.199591836734697, 5.061, 14.330897959183675, 2.572428571428572, 7.092408163265303, 276.43859183673464, 6.093551020408162, 13.501673469387757, 7.3022244897959165, 12.627673469387759, 3.7786734693877557, 34.38377551020408, 6.36761224489796, 4.29391836734694, 14.900938775510204, 9.822163265306125, 9.93057142857143, 15.399591836734695, 17.86087755102041, 6.1838775510204105, 4.33265306122449, 4.988571428571428, 16.075816326530607, 53.78340816326531, 5.602061224489796, 7.9412244897959186, 10.329897959183675, 4.41469387755102, 12.027551020408161, 8.846551020408167, 5.975489795918368, 12.957020408163261, 6.540816326530612, 31.694367346938776, 4.15665306122449, 11.461632653061224, 12.487816326530615, 6.667387755102041, 13.517163265306122, 10.366428571428568, 19.22395918367347, 12.731938775510201, 10.707857142857144, 14.851877551020408, 7.927081632653058, 10.937285714285714, 8.88679591836735, 16.02116326530612, 16.913999999999998, 6.10330612244898, 5.324632653061225, 11.086204081632651, 5.027551020408164, 6.569877551020408, 15.74689795918367, 11.405306122448982, 18.062408163265307, 1.5203061224489798, 9.009326530612244, 18.096, 5.29208163265306, 2.6772040816326528, 16.788061224489795, 8.086836734693875, 2.497653061224489, 2.3209999999999997, 6.297020408163265, 4.861367346938777, 9.642673469387756, 1.874326530612244, 6.603530612244898, 4.41108163265306, 2.9395102040816328, 4.270918367346939, 2.5894081632653063, 12.253510204081634, 17.99455102040816, 4.148632653061224, 1.8201428571428568, 6.250346938775511, 8.570265306122451, 16.082040816326533, 4.999510204081632, 16.38461224489796, 6.13212244897959, 5.375755102040817, 38.43538775510203, 7.7015918367346945, 2.9698979591836734, 3.714714285714287, 8.354122448979593, 2.351081632653061, 13.393734693877553, 6.418714285714286, 10.03408163265306, 22.121836734693883, 8.047734693877551, 10.528714285714285, 10.604224489795918, 6.680081632653064, 20.45555102040817, 15.537857142857137, 10.640551020408163, 6.683653061224492, 7.24689795918367, 15.263285714285713, 10.160224489795919, 6.841163265306121, 3.9842653061224476, 30.42791836734694, 4.887714285714285, 8.373326530612244, 36.50728571428571, 4.5810408163265315, 12.590551020408164, 4.509979591836735, 10.763326530612245, 5.718122448979591, 8.33373469387755, 17.280857142857148, 13.543122448979593, 2.318632653061224, 4.535612244897959, 6.582265306122448, 8.126775510204082, 7.981693877551019, 4.8171224489795925, 5.84504081632653, 11.521571428571429, 12.037775510204083, 15.48169387755102, 56.30979591836735, 6.093469387755102, 36.5730612244898, 6.5457959183673475, 12.139142857142861, 8.902489795918367, 17.506306122448986, 22.11867346938775, 6.254836734693878, 17.693551020408165, 13.87195918367347, 2.332326530612245, 13.632714285714286, 7.276224489795917, 17.274469387755104, 4.46269387755102, 11.928224489795918, 4.470877551020407, 5.97034693877551, 5.337, 7.022734693877553, 4.6464897959183675, 32.94410204081632, 7.831306122448981, 10.471367346938775, 6.665020408163265, 6.444816326530612, 21.06587755102041, 7.2969591836734695, 14.10240816326531, 8.518265306122448, 17.846938775510203, 26.115877551020418, 4.629938775510203, 4.726877551020407, 6.275755102040815, 9.534163265306123, 6.404081632653059, 7.86018367346939, 4.067000000000001, 181.1210612244898, 3.5674285714285707, 894.5096530612246, 4.8517551020408165, 13.439244897959181, 16.953795918367344, 12.14761224489796, 5.962142857142857, 10.119081632653062, 5.014836734693876, 4.694102040816325, 9.851346938775512, 20.941448979591833, 9.446938775510203, 8.145367346938775, 9.688734693877553, 10.14895918367347, 7.517183673469387, 4.409653061224488, 5.175877551020407, 5.951714285714287, 6.388448979591837, 4.558285714285714, 3.7377142857142864, 18.77744897959184, 4.417061224489796, 8.200591836734697, 6.107734693877551, 6.509591836734694, 7.3795510204081625, 16.399897959183676, 3.8556938775510203, 11.575448979591831, 46.36632653061226, 15.210979591836738, 8.376122448979594, 6.004142857142858, 3.4775102040816313, 4.697897959183671, 6.736346938775511, 7.2110408163265305, 10.620673469387754, 4.965122448979593, 14.314591836734692, 24.773775510204086, 17.352326530612242, 42.05810204081633, 10.160693877551024, 7.010163265306122, 6.1363877551020405, 8.923040816326532, 4.643387755102039, 11.352040816326532, 8.30842857142857, 23.052877551020405, 21.599510204081632, 5.233959183673471, 7.894448979591835, 14.70248979591837, 5.503795918367348, 2.88273469387755, 44.113326530612255, 13.706040816326533, 15.112244897959187, 25.494265306122454, 6.459857142857142, 20.5794081632653, 14.52230612244898, 18.215448979591837, 1.3194081632653063, 9.559285714285716, 15.080285714285713, 5.817265306122449, 9.664979591836737, 5.092979591836734, 5.6752448979591845, 5.745469387755101, 17.58863265306123, 10.80448979591837, 2.5311428571428567, 13.045408163265307, 5.445265306122447, 37.842591836734684, 8.39857142857143, 10.8765306122449, 9.525387755102043, 13.079244897959187, 4.8873469387755115, 10.719183673469388, 34.628408163265306, 11.67904081632653, 4.050428571428571, 25.22277551020408, 10.715591836734694, 10.30561224489796, 28.47985714285713, 9.410122448979589, 6.725510204081635, 13.688183673469386, 7.530306122448977, 33.138571428571424, 5.229673469387756, 15.698673469387758, 7.8846734693877565, 5.677612244897959, 4.250306122448979, 14.289204081632652, 5.09095918367347, 7.5477346938775485, 19.00032653061225, 20.3365306122449, 10.507632653061226, 98.99355102040816, 4.426142857142857, 5.184163265306123, 5.05730612244898, 8.565755102040814, 6.550857142857144, 20.5875306122449, 22.62828571428572, 28.808367346938788, 5.927428571428574, 6.1680408163265295, 6.798122448979593, 5.564530612244898, 25.732653061224486, 2.9530816326530616, 6.018612244897959, 6.445102040816327, 21.468142857142855, 11.57108163265306, 5.7416122448979605, 9.5144693877551, 11.35473469387755, 8.974122448979587, 9.643530612244898, 7.023510204081632, 8.558142857142858, 4.11173469387755, 11.944265306122453, 2.4455714285714283, 18.135653061224485, 18.569469387755106, 9.824265306122449, 90.35828571428573, 11.009755102040812, 9.290489795918367, 9.06330612244898, 10.89332653061224, 9.798816326530613, 11.570102040816325, 8.103571428571428, 66.76124489795917, 29.257979591836737, 26.93520408163264, 8.028489795918368, 6.081510204081632, 12.720142857142863, 5.099897959183672, 5.168714285714286, 11.026224489795915, 18.200877551020408, 11.841918367346938, 9.39112244897959, 37.75624489795918, 17.30726530612245, 16.402836734693878, 9.195489795918364, 10.204448979591836, 15.33738775510204, 8.042775510204082, 0.4189795918367348, 14.988693877551023, 7.647918367346942, 10.832142857142857, 1.3809999999999996, 1.3452448979591833, 1.3678367346938776, 8.412571428571429, 11.99508163265306, 4.353081632653062, 5.9184693877551, 2.823999999999999, 15.748000000000005, 11.159632653061225, 10.859693877551019, 8.947244897959182, 12.282469387755102, 5.796204081632655, 21.82989795918368, 31.45606122448979, 4.14095918367347, 11.049, 10.728204081632656, 15.729122448979593, 3.8785918367346923, 7.191551020408163, 83.69493877551021, 1.8085714285714287, 30.948428571428575, 12.998755102040818, 2.576102040816327, 6.2539795918367345, 3.2574285714285716, 4.416489795918369, 11.567122448979589, 50.92563265306123, 28.254367346938764, 7.523510204081633, 15.23828571428571, 4.890612244897958, 4.913244897959184, 9.711346938775511, 8.832938775510206, 19.45855102040816, 23.505530612244897, 6.856367346938779, 9.547387755102044, 6.2699795918367345, 15.356612244897962, 89.0515918367347, 4.4213061224489785, 5.430591836734695, 6.244755102040816, 7.4880408163265315, 6.553591836734693, 2.0177959183673466, 7.453346938775509, 6.752632653061225, 10.849836734693874, 1.0686122448979591, 16.5444693877551, 3.421183673469388, 11.749285714285715, 6.821102040816329, 16.407102040816326, 11.882387755102041, 5.746734693877552, 5.186632653061226, 7.858387755102042, 4.483040816326532, 7.890857142857142, 21.294326530612246, 3.3758775510204084, 4.739020408163266, 2.8817346938775508, 6.052857142857146, 13.353775510204088, 6.350836734693877, 3.906326530612246, 7.099938775510206, 2.8369183673469385, 4.368306122448981, 28.895163265306124, 13.89587755102041, 1.9647959183673467, 5.204734693877552, 3.0135918367346934, 6.492551020408162, 2.7521224489795917, 2.8015510204081635, 4.187244897959184, 5.30726530612245, 8.171795918367348, 176.03187755102047, 4.838367346938775, 4.26830612244898, 5.343571428571428, 3.888897959183673, 8.575122448979592, 19.259142857142855, 5.3313673469387775, 4.929795918367348, 2.6952448979591836, 19.777938775510208, 0.39104081632653065, 4.130510204081633, 7.428448979591837, 180.46738775510192, 7.235510204081633, 2.819530612244898, 22.611061224489802, 6.739265306122448, 15.164428571428576, 11.597673469387754, 32.42038775510205, 16.21677551020408, 7.176489795918368, 14.725551020408169, 6.899142857142855, 5.466612244897958, 13.799693877551022, 5.901979591836736, 16.407163265306124, 12.879346938775507, 15.174428571428573, 21.310775510204078, 6.337061224489798, 3.4412448979591836, 5.165571428571428, 10.38795918367347, 9.412061224489797, 10.106244897959183, 12.545530612244898, 7.828510204081637, 10.866265306122449, 12.201040816326529, 5.656816326530614, 14.65038775510204, 44.70055102040818, 33.10655102040817, 6.99465306122449, 14.136857142857146, 26.602163265306128, 4.597816326530614, 6.7889387755102035, 43.458714285714265, 18.23665306122449, 13.642020408163264, 15.557387755102043, 30.138163265306122, 30.930040816326528, 7.39438775510204, 28.87173469387755, 5.685326530612243, 8.82777551020408, 10.947061224489799, 6.0972448979591825, 5.413734693877552, 3.3784897959183664, 6.4047551020408156, 6.576163265306122, 10.94134693877551, 16.113693877551018, 5.1562857142857155, 21.216306122448977, 3.9695714285714283, 14.119163265306126, 12.69510204081633, 12.921448979591835, 5.723061224489797, 29.140367346938778, 8.345183673469387, 3.251653061224489, 5.235204081632652, 51.01671428571429, 2.9853061224489803, 8.115367346938774, 5.885265306122449, 3.7127346938775525, 5.745673469387755, 4.4497755102040815, 4.490714285714286, 23.823755102040813, 20.7709387755102, 6.464408163265306, 7.683061224489793, 7.453938775510202, 58.90746938775511, 12.655448979591831, 5.963163265306121, 47.101897959183674, 11.171469387755101, 4.270367346938777, 7.220591836734693, 2.031612244897959, 11.948244897959183, 13.042142857142858, 19.756918367346934, 10.366857142857144, 13.387979591836736, 1.1248775510204079, 22.99573469387755, 0.28502040816326535, 8.146551020408165, 4.750551020408166, 10.489816326530612, 8.018979591836734, 32.90100000000002, 7.799326530612246, 4.531061224489797, 32.48953061224489, 3.333040816326531, 3.676632653061224, 2.959020408163265, 8.173489795918368, 14.599714285714283, 4.498591836734693, 6.681326530612246, 4.280489795918366, 12.914897959183673, 11.266183673469385, 7.206244897959186, 5.547551020408163, 11.484836734693879, 2.2546734693877557, 4.080918367346941, 9.795020408163262, 12.458285714285717, 3.846040816326531, 2.585530612244898, 10.808755102040816, 7.898673469387758, 34.019938775510205, 16.67771428571428, 6.658408163265305, 6.473653061224494, 10.523857142857144, 4.34273469387755, 8.814693877551017, 21.93361224489796, 6.652183673469389, 7.366408163265309, 3.8428775510204085, 5.583326530612244, 16.847387755102037, 6.089999999999999, 3.454061224489795, 8.256489795918368, 1.4415306122448979, 17.799489795918365, 10.525530612244898, 6.116061224489795, 85.89195918367345]
	var data = [100.0, 95.83333333333334, 67.44186046511628, 74.46808510638297, 50.0, 54.347826086956516, 61.702127659574465, 53.191489361702125, 60.416666666666664, 67.3469387755102, 57.14285714285714, 68.75, 61.224489795918366, 65.3061224489796, 77.55102040816327, 58.333333333333336, 61.224489795918366, 73.91304347826086, 76.08695652173914, 75.0, 65.3061224489796, 87.5, 70.2127659574468, 79.59183673469387, 63.26530612244898, 57.14285714285714, 71.42857142857143, 40.816326530612244, 55.10204081632652, 81.63265306122449, 81.63265306122449, 53.06122448979592, 69.38775510204081, 55.10204081632652, 78.72340425531915, 57.14285714285714, 58.69565217391305, 75.51020408163265, 81.63265306122449, 57.14285714285714, 65.3061224489796, 59.183673469387756, 71.42857142857143, 67.3469387755102, 65.85365853658537, 63.26530612244898, 61.224489795918366, 75.51020408163265, 55.10204081632652, 59.57446808510638, 63.26530612244898, 75.51020408163265, 59.183673469387756, 63.26530612244898, 71.42857142857143, 65.3061224489796, 71.42857142857143, 53.06122448979592, 67.3469387755102, 65.3061224489796, 68.75, 60.416666666666664, 75.51020408163265, 69.38775510204081, 72.3404255319149, 73.46938775510205, 63.26530612244898, 60.416666666666664, 75.51020408163265, 69.38775510204081, 46.93877551020408, 46.93877551020408, 59.183673469387756, 65.3061224489796, 87.75510204081633, 59.183673469387756, 63.26530612244898, 71.42857142857143, 63.26530612244898, 48.97959183673469, 72.91666666666666, 48.97959183673469, 63.26530612244898, 57.14285714285714, 53.191489361702125, 79.59183673469387, 65.3061224489796, 75.51020408163265, 48.97959183673469, 53.65853658536586, 55.10204081632652, 75.0, 69.38775510204081, 77.08333333333334, 51.02040816326531, 67.3469387755102, 51.02040816326531, 97.95918367346938, 77.55102040816327, 69.38775510204081, 79.59183673469387, 77.55102040816327, 69.56521739130434, 53.06122448979592, 71.42857142857143, 82.97872340425532, 63.26530612244898, 63.26530612244898, 55.10204081632652, 63.26530612244898, 65.3061224489796, 77.55102040816327, 63.26530612244898, 46.93877551020408, 51.02040816326531, 53.06122448979592, 66.66666666666666, 51.02040816326531, 55.10204081632652, 48.97959183673469, 62.5, 82.97872340425532, 75.0, 59.183673469387756, 61.224489795918366, 57.14285714285714, 61.224489795918366, 51.02040816326531, 65.3061224489796, 59.183673469387756, 65.3061224489796, 46.93877551020408, 69.38775510204081, 54.166666666666664, 76.59574468085107, 69.38775510204081, 68.75, 48.97959183673469, 81.25, 65.3061224489796, 61.224489795918366, 69.38775510204081, 65.3061224489796, 55.10204081632652, 67.3469387755102, 69.38775510204081, 87.75510204081633, 58.333333333333336, 81.63265306122449, 59.183673469387756, 68.08510638297872, 85.71428571428571, 69.38775510204081, 53.06122448979592, 59.183673469387756, 57.14285714285714, 83.6734693877551, 73.46938775510205, 55.10204081632652, 51.02040816326531, 57.14285714285714, 79.16666666666666, 51.02040816326531, 59.183673469387756, 77.55102040816327, 59.183673469387756, 73.46938775510205, 65.3061224489796, 63.26530612244898, 69.38775510204081, 59.183673469387756, 63.26530612244898, 61.224489795918366, 38.775510204081634, 57.446808510638306, 62.5, 77.55102040816327, 51.02040816326531, 59.183673469387756, 62.5, 61.224489795918366, 55.10204081632652, 44.89795918367347, 77.55102040816327, 70.83333333333334, 63.26530612244898, 57.446808510638306, 60.416666666666664, 71.42857142857143, 61.224489795918366, 70.83333333333334, 71.42857142857143, 71.42857142857143, 36.734693877551024, 76.59574468085107, 63.26530612244898, 63.26530612244898, 79.59183673469387, 59.183673469387756, 57.14285714285714, 53.06122448979592, 59.183673469387756, 55.10204081632652, 59.183673469387756, 73.46938775510205, 59.183673469387756, 81.25, 59.183673469387756, 73.46938775510205, 35.41666666666667, 77.55102040816327, 72.3404255319149, 75.0, 63.26530612244898, 53.06122448979592, 75.51020408163265, 62.5, 79.59183673469387, 55.10204081632652, 75.51020408163265, 77.08333333333334, 67.3469387755102, 67.3469387755102, 61.224489795918366, 87.5, 57.14285714285714, 69.38775510204081, 67.3469387755102, 51.02040816326531, 57.14285714285714, 61.224489795918366, 50.0, 83.33333333333334, 60.416666666666664, 77.55102040816327, 39.58333333333333, 67.3469387755102, 63.26530612244898, 66.66666666666666, 85.71428571428571, 48.97959183673469, 48.97959183673469, 62.5, 67.3469387755102, 57.14285714285714, 61.224489795918366, 61.224489795918366, 51.02040816326531, 63.26530612244898, 48.97959183673469, 40.816326530612244, 79.59183673469387, 87.75510204081633, 71.42857142857143, 61.224489795918366, 51.02040816326531, 46.93877551020408, 59.183673469387756, 72.91666666666666, 56.25, 67.3469387755102, 83.6734693877551, 83.6734693877551, 70.83333333333334, 59.183673469387756, 63.26530612244898, 59.183673469387756, 57.14285714285714, 57.14285714285714, 67.3469387755102, 51.02040816326531, 55.10204081632652, 89.58333333333334, 59.183673469387756, 75.51020408163265, 51.02040816326531, 81.63265306122449, 53.06122448979592, 73.46938775510205, 57.14285714285714, 59.183673469387756, 64.58333333333334, 67.3469387755102, 51.02040816326531, 70.2127659574468, 53.06122448979592, 63.26530612244898, 72.91666666666666, 64.58333333333334, 67.3469387755102, 82.6086956521739, 65.3061224489796, 63.26530612244898, 57.14285714285714, 77.55102040816327, 57.14285714285714, 40.816326530612244, 63.26530612244898, 53.06122448979592, 63.26530612244898, 73.46938775510205, 48.97959183673469, 48.97959183673469, 73.46938775510205, 67.3469387755102, 48.97959183673469, 88.63636363636364, 61.224489795918366, 59.183673469387756, 60.86956521739131, 67.3469387755102, 81.25, 63.26530612244898, 53.06122448979592, 71.42857142857143, 71.42857142857143, 57.14285714285714, 65.3061224489796, 56.81818181818182, 66.66666666666666, 82.97872340425532, 91.83673469387756, 53.06122448979592, 61.224489795918366, 53.06122448979592, 64.58333333333334, 72.91666666666666, 65.3061224489796, 51.02040816326531, 70.2127659574468, 65.95744680851064, 77.55102040816327, 91.83673469387756, 84.44444444444444, 70.83333333333334, 71.42857142857143, 53.191489361702125, 63.26530612244898, 69.38775510204081, 61.224489795918366, 58.333333333333336, 63.26530612244898, 51.02040816326531, 59.183673469387756, 69.38775510204081, 71.42857142857143, 66.66666666666666, 46.93877551020408, 57.14285714285714, 58.333333333333336, 50.0, 71.42857142857143, 55.10204081632652, 71.42857142857143, 65.3061224489796, 55.10204081632652, 60.416666666666664, 63.26530612244898, 65.3061224489796, 54.166666666666664, 74.4186046511628, 61.224489795918366, 72.91666666666666, 59.183673469387756, 75.51020408163265, 69.38775510204081, 48.97959183673469, 59.183673469387756, 65.3061224489796, 44.89795918367347, 59.183673469387756, 64.58333333333334, 73.46938775510205, 85.41666666666666, 66.66666666666666, 87.5, 97.95918367346938, 67.3469387755102, 67.3469387755102, 59.183673469387756, 48.97959183673469, 59.183673469387756, 51.02040816326531, 57.14285714285714, 51.02040816326531, 61.224489795918366, 65.3061224489796, 55.10204081632652, 65.3061224489796, 58.333333333333336, 79.59183673469387, 48.97959183673469, 55.10204081632652, 65.3061224489796, 57.14285714285714, 77.55102040816327, 83.6734693877551, 42.857142857142854, 63.26530612244898, 55.10204081632652, 48.97959183673469, 51.02040816326531, 61.224489795918366, 77.55102040816327, 55.10204081632652, 59.183673469387756, 55.10204081632652, 48.97959183673469, 59.183673469387756, 53.06122448979592, 51.02040816326531, 44.89795918367347, 58.333333333333336, 59.183673469387756, 56.25, 69.38775510204081, 71.42857142857143, 77.55102040816327, 67.3469387755102, 79.16666666666666, 32.6530612244898, 85.71428571428571, 63.26530612244898, 41.66666666666667, 71.42857142857143, 53.06122448979592, 38.775510204081634, 69.38775510204081, 71.42857142857143, 67.3469387755102, 44.89795918367347, 60.416666666666664, 59.183673469387756, 44.89795918367347, 67.3469387755102, 63.26530612244898, 59.183673469387756, 64.58333333333334, 63.26530612244898, 61.224489795918366, 65.3061224489796, 73.46938775510205, 81.63265306122449, 67.3469387755102, 57.14285714285714, 63.26530612244898, 51.02040816326531, 60.416666666666664, 51.02040816326531, 53.06122448979592, 53.06122448979592, 51.02040816326531, 51.02040816326531, 46.93877551020408, 52.083333333333336, 55.10204081632652, 57.14285714285714, 69.38775510204081, 58.333333333333336, 77.08333333333334, 55.10204081632652, 61.224489795918366, 47.91666666666667, 62.5, 55.10204081632652, 55.10204081632652, 53.06122448979592, 63.26530612244898, 76.59574468085107, 51.02040816326531, 71.42857142857143, 58.333333333333336, 46.93877551020408, 79.59183673469387, 59.183673469387756, 46.93877551020408, 51.02040816326531, 69.38775510204081, 77.77777777777779, 53.06122448979592, 59.183673469387756, 59.183673469387756, 43.75, 65.3061224489796, 63.26530612244898, 48.97959183673469, 57.14285714285714, 71.42857142857143, 50.0, 69.38775510204081, 75.0, 42.857142857142854, 65.3061224489796, 55.10204081632652, 59.183673469387756, 55.10204081632652, 38.775510204081634, 77.55102040816327, 73.91304347826086, 63.26530612244898, 59.183673469387756, 48.97959183673469, 63.26530612244898, 59.183673469387756, 59.183673469387756, 61.224489795918366, 59.183673469387756, 48.97959183673469, 83.6734693877551, 61.224489795918366, 65.3061224489796, 67.3469387755102, 55.10204081632652, 51.02040816326531, 51.02040816326531, 51.02040816326531, 73.46938775510205, 53.06122448979592, 57.14285714285714, 51.02040816326531, 44.89795918367347, 55.10204081632652, 51.02040816326531, 75.51020408163265, 69.38775510204081, 46.93877551020408, 42.857142857142854, 65.3061224489796, 72.3404255319149, 70.83333333333334, 48.97959183673469, 55.10204081632652, 48.97959183673469, 48.97959183673469, 71.42857142857143, 81.63265306122449, 65.3061224489796, 83.6734693877551, 48.97959183673469, 55.10204081632652, 71.42857142857143, 57.14285714285714, 51.02040816326531, 63.26530612244898, 62.5, 69.38775510204081, 57.14285714285714, 46.93877551020408, 71.42857142857143, 63.26530612244898, 61.224489795918366, 65.3061224489796, 46.93877551020408, 61.224489795918366, 61.224489795918366, 55.10204081632652, 53.06122448979592, 65.3061224489796, 53.06122448979592, 53.06122448979592, 65.3061224489796, 63.26530612244898, 67.3469387755102, 53.06122448979592, 57.14285714285714, 71.42857142857143, 64.58333333333334, 65.3061224489796, 60.416666666666664, 51.02040816326531, 47.91666666666667, 59.183673469387756, 55.10204081632652, 63.26530612244898, 61.224489795918366, 51.02040816326531, 51.02040816326531, 70.83333333333334, 55.10204081632652, 64.58333333333334, 28.57142857142857, 61.224489795918366, 58.333333333333336, 51.02040816326531, 65.3061224489796, 57.14285714285714, 57.14285714285714, 55.10204081632652, 56.25, 55.10204081632652, 63.26530612244898, 48.97959183673469, 43.75, 46.93877551020408, 63.26530612244898, 64.58333333333334, 59.183673469387756, 59.183673469387756, 65.3061224489796, 65.3061224489796, 55.10204081632652, 61.224489795918366, 65.3061224489796, 51.02040816326531, 48.97959183673469, 64.44444444444444, 42.857142857142854, 46.93877551020408, 63.26530612244898, 48.97959183673469, 65.3061224489796, 79.16666666666666, 55.10204081632652, 55.10204081632652, 72.91666666666666, 65.3061224489796, 65.3061224489796, 57.14285714285714, 65.3061224489796, 42.857142857142854, 51.02040816326531, 81.63265306122449, 53.06122448979592, 69.38775510204081, 67.3469387755102, 53.06122448979592, 46.93877551020408, 48.97959183673469, 70.83333333333334, 73.46938775510205, 59.183673469387756, 75.0, 51.02040816326531, 44.89795918367347, 67.3469387755102, 44.89795918367347, 51.02040816326531, 60.416666666666664, 63.26530612244898, 57.14285714285714, 75.51020408163265, 60.416666666666664, 69.38775510204081, 73.46938775510205, 67.3469387755102, 73.46938775510205, 57.14285714285714, 53.06122448979592, 70.2127659574468, 53.06122448979592, 73.46938775510205, 59.183673469387756, 69.38775510204081, 46.93877551020408, 59.183673469387756, 44.89795918367347, 46.93877551020408, 48.97959183673469, 81.63265306122449, 46.93877551020408, 60.416666666666664, 64.58333333333334, 59.183673469387756, 51.02040816326531, 71.42857142857143, 62.5, 61.224489795918366, 64.58333333333334, 62.5, 58.333333333333336, 51.02040816326531, 76.59574468085107, 71.42857142857143, 67.3469387755102, 62.5, 48.97959183673469, 63.829787234042556, 56.25, 75.51020408163265, 71.42857142857143, 57.14285714285714, 65.21739130434783, 61.224489795918366, 69.38775510204081, 79.59183673469387, 69.38775510204081, 46.93877551020408, 46.93877551020408, 81.63265306122449, 55.10204081632652, 77.55102040816327, 53.06122448979592, 55.10204081632652, 55.10204081632652, 70.2127659574468, 58.333333333333336, 44.89795918367347, 53.06122448979592, 59.183673469387756, 67.3469387755102, 56.52173913043478, 65.3061224489796, 71.42857142857143, 42.857142857142854, 47.91666666666667, 53.06122448979592, 68.75, 59.183673469387756, 63.26530612244898, 59.183673469387756, 79.59183673469387, 53.06122448979592, 53.06122448979592, 65.3061224489796, 59.183673469387756, 48.97959183673469, 55.10204081632652, 67.3469387755102, 51.02040816326531, 65.3061224489796, 69.38775510204081, 54.166666666666664, 55.10204081632652, 57.14285714285714, 53.06122448979592, 73.91304347826086, 59.183673469387756, 72.91666666666666, 55.10204081632652, 65.3061224489796, 47.91666666666667, 53.06122448979592, 55.10204081632652, 40.816326530612244, 85.71428571428571, 57.14285714285714, 71.42857142857143, 59.183673469387756, 67.3469387755102, 55.10204081632652, 58.333333333333336, 54.166666666666664, 57.14285714285714, 61.224489795918366, 61.224489795918366, 61.224489795918366, 67.3469387755102, 69.38775510204081, 65.3061224489796, 71.42857142857143, 77.08333333333334, 66.66666666666666, 61.224489795918366, 53.06122448979592, 48.97959183673469, 55.10204081632652, 73.46938775510205, 70.83333333333334, 66.66666666666666, 53.06122448979592, 67.3469387755102, 63.26530612244898, 48.97959183673469, 61.224489795918366, 68.75, 40.816326530612244, 46.93877551020408, 61.224489795918366, 57.14285714285714, 70.2127659574468, 63.26530612244898, 67.3469387755102, 51.02040816326531, 57.14285714285714, 63.26530612244898, 66.66666666666666, 54.166666666666664, 46.93877551020408, 26.53061224489796, 71.42857142857143, 44.89795918367347, 59.183673469387756, 48.97959183673469, 44.89795918367347, 79.59183673469387, 57.14285714285714, 42.857142857142854, 69.38775510204081, 34.69387755102041, 61.224489795918366, 48.97959183673469, 66.66666666666666, 65.3061224489796, 53.06122448979592, 44.89795918367347, 55.10204081632652, 75.51020408163265, 73.46938775510205, 58.333333333333336, 65.3061224489796, 44.89795918367347, 53.06122448979592, 55.10204081632652, 69.38775510204081, 71.42857142857143, 55.10204081632652, 65.3061224489796, 53.06122448979592, 59.183673469387756, 55.10204081632652, 60.416666666666664, 51.02040816326531, 53.06122448979592, 53.06122448979592, 50.0, 57.14285714285714, 57.14285714285714, 55.10204081632652, 66.66666666666666, 48.97959183673469, 79.16666666666666, 57.14285714285714, 63.26530612244898, 55.10204081632652, 67.3469387755102, 61.224489795918366, 67.3469387755102, 59.183673469387756, 69.38775510204081, 68.75, 47.91666666666667, 51.02040816326531, 60.416666666666664, 48.97959183673469, 53.06122448979592, 58.333333333333336, 59.183673469387756, 63.26530612244898, 53.06122448979592, 69.38775510204081, 79.59183673469387, 59.183673469387756, 65.3061224489796, 83.33333333333334, 69.38775510204081, 57.14285714285714, 44.89795918367347, 51.02040816326531, 67.3469387755102, 65.3061224489796, 44.89795918367347, 44.89795918367347, 59.183673469387756, 61.224489795918366, 80.85106382978722, 69.38775510204081, 67.3469387755102, 91.83673469387756, 63.26530612244898, 50.0, 75.51020408163265, 75.51020408163265, 51.02040816326531, 73.46938775510205, 93.87755102040816, 67.3469387755102, 69.38775510204081, 73.46938775510205, 63.26530612244898, 59.183673469387756, 63.26530612244898, 57.14285714285714, 65.3061224489796, 63.26530612244898, 63.26530612244898, 59.183673469387756, 73.46938775510205, 59.183673469387756, 61.224489795918366, 59.183673469387756, 59.183673469387756, 77.55102040816327, 58.333333333333336, 63.26530612244898, 48.97959183673469, 75.51020408163265, 62.5, 73.46938775510205, 61.224489795918366, 52.083333333333336, 57.14285714285714, 51.02040816326531, 60.416666666666664, 48.97959183673469, 59.183673469387756, 63.26530612244898, 65.3061224489796, 57.14285714285714, 73.46938775510205, 44.89795918367347, 75.51020408163265, 53.06122448979592, 48.97959183673469, 51.02040816326531, 61.224489795918366, 57.14285714285714, 51.02040816326531, 67.3469387755102, 57.14285714285714, 83.6734693877551, 55.10204081632652, 61.224489795918366, 55.10204081632652, 69.38775510204081, 63.26530612244898, 60.416666666666664, 55.319148936170215, 36.734693877551024, 51.02040816326531, 69.38775510204081, 34.69387755102041, 46.93877551020408, 59.183673469387756, 53.06122448979592, 72.91666666666666, 63.26530612244898, 46.93877551020408, 48.97959183673469, 59.183673469387756, 59.183673469387756, 65.3061224489796, 57.14285714285714, 60.416666666666664, 48.97959183673469, 61.224489795918366, 65.3061224489796, 42.857142857142854, 65.3061224489796, 79.59183673469387, 67.3469387755102, 75.51020408163265, 53.06122448979592, 53.06122448979592, 51.02040816326531, 38.775510204081634, 73.46938775510205, 59.183673469387756, 57.14285714285714, 59.183673469387756, 71.42857142857143, 40.816326530612244, 77.55102040816327, 53.06122448979592, 48.97959183673469, 71.42857142857143, 53.06122448979592, 55.10204081632652, 59.183673469387756, 53.06122448979592, 63.26530612244898, 46.93877551020408, 57.14285714285714, 81.63265306122449, 48.97959183673469, 61.224489795918366, 61.224489795918366, 47.91666666666667, 57.14285714285714, 57.14285714285714, 36.734693877551024, 57.14285714285714, 63.26530612244898, 57.14285714285714, 67.3469387755102, 61.224489795918366, 83.6734693877551, 73.46938775510205, 61.224489795918366, 55.10204081632652, 61.224489795918366, 71.42857142857143, 46.93877551020408, 57.14285714285714, 57.14285714285714, 67.3469387755102, 55.10204081632652, 57.14285714285714, 67.3469387755102, 61.224489795918366, 67.3469387755102, 62.5, 61.224489795918366, 61.224489795918366, 46.93877551020408, 42.857142857142854, 52.083333333333336, 77.08333333333334, 46.93877551020408, 57.14285714285714, 55.10204081632652, 58.333333333333336, 48.97959183673469, 61.224489795918366, 65.3061224489796, 51.02040816326531, 65.3061224489796, 61.224489795918366, 55.10204081632652, 75.0, 59.183673469387756, 45.83333333333333, 57.14285714285714, 48.97959183673469, 46.93877551020408, 61.224489795918366, 46.93877551020408, 57.14285714285714, 79.59183673469387, 51.02040816326531, 77.55102040816327, 61.224489795918366, 68.75, 46.93877551020408, 67.3469387755102, 53.06122448979592, 67.3469387755102, 46.93877551020408, 63.26530612244898, 75.51020408163265, 61.224489795918366, 48.97959183673469, 66.66666666666666, 51.02040816326531, 57.14285714285714, 47.91666666666667, 62.5, 61.224489795918366, 51.02040816326531, 51.02040816326531, 57.14285714285714, 83.6734693877551, 71.42857142857143, 36.734693877551024, 75.51020408163265, 42.857142857142854, 40.816326530612244, 55.10204081632652, 71.42857142857143, 69.38775510204081, 55.10204081632652, 50.0, 73.46938775510205, 55.10204081632652, 48.97959183673469, 53.06122448979592, 61.224489795918366, 61.224489795918366, 55.10204081632652, 65.3061224489796, 57.14285714285714, 69.38775510204081, 51.02040816326531, 51.02040816326531, 69.38775510204081, 67.3469387755102, 48.97959183673469, 65.3061224489796, 40.816326530612244, 50.0, 59.183673469387756, 77.08333333333334, 61.224489795918366, 65.3061224489796, 57.14285714285714, 65.3061224489796, 81.25, 57.14285714285714, 44.89795918367347, 53.06122448979592, 53.06122448979592, 57.14285714285714, 57.14285714285714, 63.26530612244898, 77.55102040816327, 73.46938775510205, 67.3469387755102, 65.3061224489796, 55.10204081632652, 75.51020408163265, 57.14285714285714, 77.55102040816327, 64.58333333333334, 53.06122448979592, 46.93877551020408, 53.06122448979592, 67.3469387755102, 55.10204081632652, 55.10204081632652, 67.3469387755102, 53.06122448979592, 51.02040816326531, 77.55102040816327, 77.55102040816327, 55.10204081632652, 66.66666666666666, 57.14285714285714, 71.42857142857143, 75.51020408163265, 63.26530612244898, 61.702127659574465, 83.6734693877551, 69.38775510204081, 61.224489795918366, 53.06122448979592, 71.42857142857143, 59.183673469387756, 77.08333333333334, 69.38775510204081, 59.183673469387756, 73.46938775510205, 65.3061224489796, 62.5, 63.26530612244898, 54.166666666666664, 73.46938775510205, 66.66666666666666, 46.93877551020408, 57.14285714285714, 69.38775510204081, 69.38775510204081, 61.224489795918366, 57.14285714285714, 35.41666666666667, 56.25, 59.183673469387756, 51.02040816326531, 73.46938775510205, 63.26530612244898, 51.02040816326531, 83.6734693877551, 51.02040816326531, 51.02040816326531, 43.75, 48.97959183673469, 51.02040816326531, 73.46938775510205, 48.97959183673469, 58.333333333333336, 48.97959183673469, 67.3469387755102, 51.02040816326531, 73.46938775510205, 64.58333333333334, 65.3061224489796, 63.26530612244898, 59.183673469387756, 65.3061224489796, 55.10204081632652, 75.51020408163265, 57.14285714285714, 71.42857142857143, 68.75, 46.93877551020408, 63.26530612244898, 75.0, 63.26530612244898, 65.3061224489796, 65.3061224489796, 72.91666666666666, 75.51020408163265, 70.83333333333334, 64.58333333333334, 70.83333333333334, 63.26530612244898, 59.183673469387756, 53.06122448979592, 47.91666666666667, 69.38775510204081, 67.3469387755102, 71.42857142857143, 67.3469387755102, 44.89795918367347, 57.14285714285714, 48.97959183673469, 63.26530612244898, 67.3469387755102, 61.224489795918366, 55.10204081632652, 65.3061224489796, 73.46938775510205, 53.06122448979592, 79.59183673469387, 53.06122448979592, 51.02040816326531, 61.224489795918366, 65.3061224489796, 67.3469387755102, 64.58333333333334, 67.3469387755102, 66.66666666666666, 59.183673469387756, 46.93877551020408, 73.46938775510205, 62.5, 45.83333333333333, 46.93877551020408, 78.72340425531915, 57.14285714285714, 59.183673469387756, 75.51020408163265, 62.5, 63.26530612244898, 59.183673469387756, 71.42857142857143, 55.10204081632652, 62.5, 60.416666666666664, 59.183673469387756, 44.89795918367347, 52.083333333333336, 48.97959183673469, 44.89795918367347, 63.26530612244898, 68.75, 65.3061224489796, 57.14285714285714, 63.26530612244898, 53.06122448979592, 64.58333333333334, 53.06122448979592, 77.55102040816327, 42.857142857142854, 91.30434782608695, 59.183673469387756, 53.06122448979592, 71.42857142857143, 79.59183673469387, 51.02040816326531, 48.97959183673469, 59.183673469387756, 57.14285714285714, 77.55102040816327, 70.83333333333334, 64.58333333333334, 46.93877551020408, 46.93877551020408, 63.26530612244898, 53.06122448979592, 61.224489795918366, 61.224489795918366, 46.93877551020408, 71.42857142857143, 57.14285714285714, 71.42857142857143, 51.02040816326531, 65.3061224489796, 70.2127659574468, 51.02040816326531, 61.224489795918366, 55.10204081632652, 55.10204081632652, 71.42857142857143, 46.93877551020408, 55.10204081632652, 65.3061224489796, 55.319148936170215, 73.46938775510205, 87.2340425531915, 69.38775510204081, 51.02040816326531, 65.3061224489796, 71.42857142857143, 51.02040816326531, 59.183673469387756, 57.14285714285714, 48.97959183673469, 51.02040816326531, 63.26530612244898, 63.26530612244898, 67.3469387755102, 57.14285714285714, 46.93877551020408, 63.26530612244898, 61.224489795918366, 73.46938775510205, 66.66666666666666, 63.26530612244898, 55.10204081632652, 73.46938775510205, 56.25, 81.63265306122449, 59.183673469387756, 53.06122448979592, 65.3061224489796, 65.3061224489796, 80.43478260869566, 44.89795918367347, 65.3061224489796, 65.3061224489796, 87.75510204081633, 72.3404255319149, 63.26530612244898, 57.14285714285714, 46.93877551020408, 69.38775510204081, 65.3061224489796, 65.3061224489796, 83.6734693877551, 81.63265306122449, 70.83333333333334, 66.66666666666666, 68.75, 71.42857142857143, 65.3061224489796, 58.333333333333336, 69.38775510204081, 51.02040816326531, 77.55102040816327, 44.89795918367347, 48.97959183673469, 72.91666666666666, 55.10204081632652, 88.88888888888889, 55.10204081632652, 67.3469387755102, 53.06122448979592, 65.3061224489796, 57.14285714285714, 62.5, 40.816326530612244, 73.46938775510205, 75.51020408163265, 63.26530612244898, 56.25, 51.02040816326531, 71.42857142857143, 79.59183673469387, 67.3469387755102, 61.224489795918366, 77.55102040816327, 77.55102040816327, 55.10204081632652, 61.224489795918366, 47.91666666666667, 69.38775510204081, 79.59183673469387, 71.42857142857143, 77.55102040816327, 77.55102040816327, 67.3469387755102, 61.224489795918366, 58.139534883720934, 60.416666666666664, 63.26530612244898, 65.3061224489796, 44.89795918367347, 67.3469387755102, 69.38775510204081, 55.319148936170215, 71.42857142857143, 48.97959183673469, 57.14285714285714, 69.56521739130434, 61.224489795918366, 51.02040816326531, 61.224489795918366, 71.42857142857143, 46.93877551020408, 53.06122448979592, 69.38775510204081, 55.10204081632652, 69.38775510204081, 57.14285714285714, 67.3469387755102, 77.55102040816327, 70.83333333333334, 79.16666666666666, 51.02040816326531, 61.224489795918366, 65.3061224489796, 91.83673469387756, 61.224489795918366, 65.3061224489796, 55.10204081632652, 67.3469387755102, 48.97959183673469, 74.46808510638297, 62.5, 44.89795918367347, 70.2127659574468, 77.55102040816327, 69.38775510204081, 65.95744680851064, 78.26086956521739, 65.95744680851064, 59.183673469387756, 59.183673469387756, 69.38775510204081, 67.3469387755102, 68.75, 67.3469387755102, 67.3469387755102, 47.91666666666667, 55.10204081632652, 71.42857142857143, 72.91666666666666, 53.06122448979592, 57.14285714285714, 56.25, 68.75, 83.6734693877551, 85.41666666666666, 77.08333333333334, 67.3469387755102, 65.3061224489796, 42.857142857142854, 63.26530612244898, 63.829787234042556, 67.3469387755102, 56.25, 59.183673469387756, 59.183673469387756, 55.10204081632652, 65.3061224489796, 65.3061224489796, 48.97959183673469, 63.26530612244898, 42.857142857142854, 50.0, 79.16666666666666, 67.3469387755102, 73.46938775510205, 53.06122448979592, 73.46938775510205, 79.59183673469387, 62.5, 63.26530612244898, 67.3469387755102, 67.3469387755102, 71.42857142857143, 57.14285714285714, 65.3061224489796, 65.3061224489796, 65.3061224489796, 69.38775510204081, 50.0, 59.183673469387756, 42.857142857142854, 63.26530612244898, 83.6734693877551, 67.3469387755102, 65.3061224489796, 53.06122448979592, 61.224489795918366, 51.02040816326531, 63.26530612244898, 70.83333333333334, 75.51020408163265, 51.02040816326531, 77.55102040816327, 79.59183673469387, 66.66666666666666, 65.3061224489796, 68.75, 62.5, 55.10204081632652, 57.14285714285714, 62.5, 63.26530612244898, 75.51020408163265, 55.10204081632652, 48.97959183673469, 73.46938775510205, 59.183673469387756, 46.93877551020408, 59.183673469387756, 59.183673469387756, 52.083333333333336, 67.3469387755102, 77.55102040816327, 63.26530612244898, 53.06122448979592, 53.06122448979592, 55.10204081632652, 65.3061224489796, 53.06122448979592, 68.75, 81.63265306122449, 55.10204081632652, 67.3469387755102, 61.224489795918366, 65.3061224489796, 61.224489795918366, 65.3061224489796, 63.26530612244898, 87.75510204081633, 65.3061224489796, 57.14285714285714, 77.08333333333334, 63.26530612244898, 46.93877551020408, 57.14285714285714, 67.3469387755102, 69.38775510204081, 77.55102040816327, 71.42857142857143, 60.416666666666664, 65.3061224489796, 67.3469387755102, 70.83333333333334, 46.93877551020408, 59.57446808510638, 63.26530612244898, 57.14285714285714, 61.224489795918366, 59.183673469387756, 71.42857142857143, 65.3061224489796, 53.06122448979592, 64.58333333333334, 55.10204081632652, 65.3061224489796, 59.183673469387756, 66.66666666666666, 71.42857142857143, 51.06382978723404, 66.66666666666666, 85.71428571428571, 65.3061224489796, 71.42857142857143, 40.0, 64.58333333333334, 61.224489795918366, 54.166666666666664, 65.3061224489796, 57.14285714285714, 59.183673469387756, 51.02040816326531, 65.3061224489796, 53.06122448979592, 63.26530612244898, 67.3469387755102, 59.183673469387756, 71.42857142857143, 73.46938775510205, 69.38775510204081, 79.59183673469387, 68.08510638297872, 59.183673469387756, 81.63265306122449, 65.3061224489796, 51.02040816326531, 71.42857142857143, 55.10204081632652, 81.63265306122449, 50.0, 65.3061224489796, 79.59183673469387, 68.75, 67.3469387755102, 67.3469387755102, 55.10204081632652, 67.3469387755102, 65.3061224489796, 81.63265306122449, 64.58333333333334, 75.51020408163265, 59.183673469387756, 57.14285714285714, 57.14285714285714, 71.42857142857143, 69.38775510204081, 59.183673469387756, 67.3469387755102, 73.46938775510205, 83.6734693877551, 57.14285714285714, 42.857142857142854, 50.0, 63.26530612244898, 72.91666666666666, 67.3469387755102, 70.83333333333334, 75.51020408163265, 77.55102040816327, 53.191489361702125, 71.42857142857143, 79.59183673469387, 75.0, 57.14285714285714, 55.10204081632652, 63.26530612244898, 61.702127659574465, 73.46938775510205, 55.10204081632652, 75.55555555555556, 73.46938775510205, 51.02040816326531, 69.38775510204081, 73.46938775510205, 75.51020408163265, 66.66666666666666, 67.3469387755102, 65.95744680851064, 75.51020408163265, 53.06122448979592, 63.26530612244898, 67.3469387755102, 59.183673469387756, 42.857142857142854, 44.89795918367347, 58.333333333333336, 60.416666666666664, 65.3061224489796, 67.3469387755102, 61.224489795918366, 53.191489361702125, 55.10204081632652, 63.26530612244898, 77.55102040816327, 79.59183673469387, 53.06122448979592, 71.42857142857143, 71.42857142857143, 67.3469387755102, 77.55102040816327, 78.72340425531915, 53.06122448979592, 51.02040816326531, 59.183673469387756, 73.46938775510205, 47.91666666666667, 50.0, 75.51020408163265, 75.51020408163265, 70.83333333333334, 71.42857142857143, 67.3469387755102, 87.75510204081633, 57.14285714285714, 55.10204081632652, 61.702127659574465, 81.63265306122449, 79.59183673469387, 42.857142857142854, 68.75, 75.51020408163265, 42.857142857142854, 67.3469387755102, 51.02040816326531, 75.51020408163265, 65.3061224489796, 83.6734693877551, 55.10204081632652, 73.46938775510205, 71.42857142857143, 55.10204081632652, 69.38775510204081, 63.26530612244898, 53.06122448979592, 68.75, 55.10204081632652, 56.25, 55.10204081632652, 55.10204081632652, 65.3061224489796, 59.183673469387756, 67.3469387755102, 62.5, 79.59183673469387, 59.183673469387756, 53.06122448979592, 57.14285714285714, 63.26530612244898, 71.42857142857143, 55.10204081632652, 48.97959183673469, 38.775510204081634, 65.3061224489796, 65.3061224489796, 60.416666666666664, 48.97959183673469, 48.97959183673469, 62.5, 51.02040816326531, 70.83333333333334, 53.06122448979592, 66.66666666666666, 53.06122448979592, 75.51020408163265, 67.3469387755102, 61.224489795918366, 56.52173913043478, 72.91666666666666, 83.6734693877551, 57.14285714285714, 61.224489795918366, 63.26530612244898, 79.59183673469387, 51.02040816326531, 42.857142857142854, 64.58333333333334, 69.38775510204081, 48.97959183673469, 63.26530612244898, 68.08510638297872, 65.3061224489796, 73.46938775510205, 55.10204081632652, 69.38775510204081, 61.224489795918366, 60.416666666666664, 61.224489795918366, 51.02040816326531, 65.3061224489796, 47.91666666666667, 69.38775510204081, 74.46808510638297, 65.21739130434783, 58.333333333333336, 81.63265306122449, 71.42857142857143, 59.183673469387756, 61.224489795918366, 69.38775510204081, 62.5, 46.93877551020408, 59.183673469387756, 75.51020408163265, 57.446808510638306, 59.183673469387756, 67.3469387755102, 63.26530612244898, 65.3061224489796, 59.183673469387756, 51.02040816326531, 51.02040816326531, 67.3469387755102, 73.46938775510205, 81.63265306122449, 53.06122448979592, 55.10204081632652, 69.38775510204081, 73.46938775510205, 69.38775510204081, 66.66666666666666, 58.333333333333336, 61.224489795918366, 55.10204081632652, 79.59183673469387, 55.10204081632652, 55.10204081632652, 69.38775510204081, 60.416666666666664, 53.06122448979592, 73.46938775510205, 67.3469387755102, 83.6734693877551, 44.44444444444444, 44.89795918367347, 75.51020408163265, 67.3469387755102, 62.5, 57.14285714285714, 67.3469387755102, 59.183673469387756, 81.63265306122449, 71.42857142857143, 69.38775510204081, 68.75, 69.38775510204081, 53.06122448979592, 71.42857142857143, 59.183673469387756, 51.02040816326531, 79.59183673469387, 53.06122448979592, 72.91666666666666, 75.51020408163265, 67.3469387755102, 69.38775510204081, 71.42857142857143, 61.224489795918366, 75.51020408163265, 40.816326530612244, 44.89795918367347, 77.55102040816327, 59.183673469387756, 56.25, 53.06122448979592, 75.51020408163265, 77.55102040816327, 55.10204081632652, 67.3469387755102, 77.55102040816327, 55.10204081632652, 75.51020408163265, 53.06122448979592, 71.42857142857143, 63.26530612244898, 59.183673469387756, 67.3469387755102, 69.38775510204081, 63.26530612244898, 73.46938775510205, 59.183673469387756, 63.26530612244898, 58.333333333333336, 63.26530612244898, 77.55102040816327, 42.857142857142854, 55.10204081632652, 67.3469387755102, 61.224489795918366, 65.3061224489796, 53.06122448979592, 55.10204081632652, 60.416666666666664, 48.97959183673469, 51.02040816326531, 46.93877551020408, 79.59183673469387, 53.06122448979592, 66.66666666666666, 51.02040816326531, 54.166666666666664, 43.75, 48.38709677419355, 65.3061224489796, 48.97959183673469, 69.38775510204081, 65.3061224489796, 69.38775510204081, 51.02040816326531, 83.6734693877551, 52.083333333333336, 55.10204081632652, 48.97959183673469, 65.3061224489796, 46.93877551020408, 65.3061224489796, 57.14285714285714, 63.26530612244898, 63.26530612244898, 51.02040816326531, 59.183673469387756, 52.083333333333336, 75.51020408163265, 63.26530612244898, 69.56521739130434, 57.14285714285714, 48.97959183673469, 61.224489795918366, 51.02040816326531, 60.416666666666664, 77.55102040816327, 81.63265306122449, 65.3061224489796, 59.183673469387756, 48.97959183673469, 81.63265306122449, 55.10204081632652, 65.3061224489796, 77.55102040816327, 83.6734693877551, 73.46938775510205, 68.75, 75.0, 57.14285714285714, 65.95744680851064, 48.97959183673469, 71.42857142857143, 55.319148936170215, 47.91666666666667, 71.42857142857143, 77.55102040816327, 51.02040816326531, 69.38775510204081, 59.183673469387756, 55.10204081632652, 63.26530612244898, 57.14285714285714, 67.3469387755102, 53.06122448979592, 65.3061224489796, 69.38775510204081, 57.14285714285714, 53.06122448979592, 63.26530612244898, 73.46938775510205, 70.83333333333334, 71.42857142857143, 69.38775510204081, 72.91666666666666, 61.224489795918366, 63.26530612244898, 67.3469387755102, 75.51020408163265, 59.183673469387756, 75.51020408163265, 61.224489795918366, 81.63265306122449, 61.224489795918366, 51.02040816326531, 51.02040816326531, 59.183673469387756, 55.10204081632652, 53.06122448979592, 59.183673469387756, 51.02040816326531, 81.63265306122449, 63.26530612244898, 71.42857142857143, 65.21739130434783, 60.416666666666664, 61.702127659574465, 65.3061224489796, 79.59183673469387, 76.59574468085107, 59.183673469387756, 64.58333333333334, 59.183673469387756, 69.56521739130434, 73.46938775510205, 55.10204081632652, 53.06122448979592, 51.02040816326531, 55.10204081632652, 75.51020408163265, 57.14285714285714, 69.38775510204081, 54.166666666666664, 51.02040816326531, 65.3061224489796, 54.166666666666664, 65.3061224489796, 55.10204081632652, 63.26530612244898, 85.41666666666666, 71.42857142857143, 83.6734693877551, 67.3469387755102, 65.3061224489796, 53.06122448979592, 63.26530612244898, 61.224489795918366, 57.14285714285714, 63.26530612244898, 42.857142857142854, 40.816326530612244, 77.55102040816327, 63.26530612244898, 67.3469387755102, 42.857142857142854, 48.97959183673469, 65.3061224489796, 64.58333333333334, 65.3061224489796, 69.38775510204081, 59.183673469387756, 73.46938775510205, 81.63265306122449, 66.66666666666666, 65.3061224489796, 57.14285714285714, 53.06122448979592, 53.06122448979592, 59.183673469387756, 67.3469387755102, 57.14285714285714, 71.42857142857143, 53.06122448979592, 64.58333333333334, 69.38775510204081, 67.3469387755102, 77.55102040816327, 63.26530612244898, 42.857142857142854, 63.26530612244898, 65.3061224489796, 55.10204081632652, 77.55102040816327, 57.14285714285714, 57.14285714285714, 77.55102040816327, 75.51020408163265, 59.183673469387756, 60.416666666666664, 63.26530612244898, 53.06122448979592, 77.55102040816327, 56.25, 67.3469387755102, 71.42857142857143, 70.83333333333334, 53.06122448979592, 59.183673469387756, 65.3061224489796, 67.3469387755102, 70.83333333333334, 73.46938775510205, 75.51020408163265, 61.224489795918366, 73.46938775510205, 77.55102040816327, 73.46938775510205, 69.38775510204081, 51.02040816326531, 68.18181818181817, 61.224489795918366, 71.42857142857143, 44.89795918367347, 77.55102040816327, 44.89795918367347, 79.59183673469387, 81.63265306122449, 57.14285714285714, 73.46938775510205, 63.26530612244898, 67.3469387755102, 63.26530612244898, 52.083333333333336, 56.25, 57.14285714285714, 53.06122448979592, 68.75, 79.59183673469387, 55.10204081632652, 63.26530612244898, 67.3469387755102, 48.97959183673469, 57.14285714285714, 61.224489795918366, 87.75510204081633, 61.224489795918366, 67.3469387755102, 48.93617021276596, 67.3469387755102, 48.97959183673469, 65.3061224489796, 73.33333333333333, 77.08333333333334, 70.83333333333334, 76.08695652173914, 53.06122448979592, 53.06122448979592, 65.3061224489796, 65.3061224489796, 59.183673469387756, 57.14285714285714, 48.97959183673469, 63.26530612244898, 57.14285714285714, 55.10204081632652, 53.06122448979592, 65.3061224489796, 59.183673469387756, 61.224489795918366, 57.14285714285714, 60.416666666666664, 63.26530612244898, 83.6734693877551, 48.97959183673469, 67.3469387755102, 69.38775510204081, 77.55102040816327, 61.224489795918366, 54.347826086956516, 62.5, 73.46938775510205, 85.71428571428571, 65.3061224489796, 69.38775510204081, 70.2127659574468, 58.82352941176471, 63.26530612244898, 71.42857142857143, 58.333333333333336, 63.26530612244898, 81.25, 87.75510204081633, 46.808510638297875, 59.183673469387756, 67.3469387755102, 59.183673469387756, 79.16666666666666, 55.10204081632652, 71.42857142857143, 51.02040816326531, 57.446808510638306, 59.183673469387756, 61.224489795918366, 69.38775510204081, 61.224489795918366, 59.183673469387756, 51.02040816326531, 59.183673469387756, 51.02040816326531, 75.51020408163265, 67.3469387755102, 53.06122448979592, 69.38775510204081, 93.87755102040816, 51.02040816326531, 57.14285714285714, 53.191489361702125, 46.93877551020408, 46.93877551020408, 61.224489795918366, 67.3469387755102, 62.5, 66.66666666666666, 75.51020408163265, 85.41666666666666, 65.3061224489796, 66.66666666666666, 65.3061224489796, 67.3469387755102, 69.38775510204081, 72.91666666666666, 75.51020408163265, 53.06122448979592, 71.42857142857143, 57.14285714285714, 46.93877551020408, 73.46938775510205, 44.89795918367347, 53.06122448979592, 79.16666666666666, 55.10204081632652, 61.224489795918366, 46.93877551020408, 62.5, 71.42857142857143, 59.183673469387756, 71.42857142857143, 65.3061224489796, 55.10204081632652, 63.26530612244898, 67.3469387755102, 59.183673469387756, 71.42857142857143, 53.06122448979592, 79.59183673469387, 65.3061224489796, 79.59183673469387, 44.89795918367347, 61.224489795918366, 51.02040816326531, 71.42857142857143, 61.224489795918366, 63.26530612244898, 53.191489361702125, 55.10204081632652, 57.14285714285714, 61.224489795918366, 31.25, 55.10204081632652, 51.06382978723404, 55.10204081632652, 69.38775510204081, 57.14285714285714, 69.38775510204081, 42.857142857142854, 57.446808510638306, 53.06122448979592, 55.10204081632652, 67.3469387755102, 67.3469387755102, 61.224489795918366, 51.02040816326531, 55.10204081632652, 53.06122448979592, 61.224489795918366, 44.89795918367347, 55.10204081632652, 63.26530612244898, 42.857142857142854, 51.02040816326531, 65.3061224489796, 63.26530612244898, 91.83673469387756, 65.3061224489796, 55.10204081632652, 59.183673469387756, 51.02040816326531, 61.224489795918366, 48.97959183673469, 55.10204081632652, 59.183673469387756, 75.51020408163265, 73.46938775510205, 53.06122448979592, 57.14285714285714, 59.183673469387756, 81.25, 72.91666666666666, 57.14285714285714, 61.224489795918366, 55.10204081632652, 72.91666666666666, 48.97959183673469, 57.89473684210527, 51.02040816326531, 71.42857142857143, 58.333333333333336, 53.06122448979592, 52.083333333333336, 73.46938775510205, 71.42857142857143, 57.14285714285714, 87.75510204081633, 77.55102040816327, 53.06122448979592, 81.63265306122449, 59.183673469387756, 67.3469387755102, 79.16666666666666, 73.46938775510205, 71.42857142857143, 69.38775510204081, 59.183673469387756, 65.3061224489796, 62.5, 65.95744680851064, 67.3469387755102, 91.83673469387756, 71.42857142857143, 67.3469387755102, 59.183673469387756, 46.93877551020408, 55.10204081632652, 71.42857142857143, 51.02040816326531, 59.183673469387756, 61.224489795918366, 65.3061224489796, 79.59183673469387, 68.75, 79.59183673469387, 59.183673469387756, 73.46938775510205, 89.79591836734694, 77.55102040816327, 48.97959183673469, 57.14285714285714, 63.829787234042556, 73.46938775510205, 53.06122448979592, 69.38775510204081, 53.84615384615385, 46.93877551020408, 42.857142857142854, 59.183673469387756, 44.89795918367347, 69.38775510204081, 65.3061224489796, 63.26530612244898, 60.416666666666664, 59.183673469387756, 57.14285714285714, 70.2127659574468, 58.333333333333336, 65.3061224489796, 60.86956521739131, 53.06122448979592, 64.0, 81.25, 54.166666666666664, 57.14285714285714, 65.3061224489796, 63.26530612244898, 36.734693877551024, 59.183673469387756, 55.10204081632652, 51.02040816326531, 48.97959183673469, 65.3061224489796, 48.97959183673469, 75.51020408163265, 77.55102040816327, 69.38775510204081, 57.14285714285714, 54.166666666666664, 79.59183673469387, 61.224489795918366, 57.14285714285714, 67.3469387755102, 72.91666666666666, 63.26530612244898, 65.21739130434783, 71.42857142857143, 48.97959183673469, 68.08510638297872, 75.51020408163265, 69.38775510204081, 73.46938775510205, 51.02040816326531, 65.3061224489796, 51.02040816326531, 66.66666666666666, 51.02040816326531, 53.06122448979592, 73.46938775510205, 77.55102040816327, 57.14285714285714, 51.02040816326531, 71.42857142857143, 62.5, 51.02040816326531, 57.14285714285714, 57.14285714285714, 57.14285714285714, 53.06122448979592, 73.46938775510205, 63.63636363636363, 71.42857142857143, 73.46938775510205, 71.42857142857143, 61.224489795918366, 53.06122448979592, 53.06122448979592, 59.183673469387756, 73.46938775510205, 71.42857142857143, 59.183673469387756, 51.02040816326531, 61.224489795918366, 73.46938775510205, 57.14285714285714, 75.51020408163265, 67.3469387755102, 55.10204081632652, 57.446808510638306, 54.166666666666664, 51.02040816326531, 77.55102040816327, 75.51020408163265, 71.42857142857143, 51.02040816326531, 61.224489795918366, 67.3469387755102, 73.46938775510205, 56.25, 59.183673469387756, 53.06122448979592, 79.59183673469387, 87.5, 51.02040816326531, 69.38775510204081]
	var xy = data.map((e, i)=> ({"x":labels[i] , "y":data[i]} ))
	var datasets = [{
		"data": xy,
		"backgroundColor": 		"#FFA348",
		showLine: false,
	    fill: false,
	    pointRadius: 3
	}];
	var data = {
		"datasets": datasets,
		"labels": labels
	}
	var ctx = document.getElementById('accuracy_time').getContext('2d');
	var myPieChart = new Chart(ctx,{
	    type: 'scatter',
	    data: data,
	    options: {
	    	legend:{
	    		display: false
	    	},
	    	plugins:{
	    		datalabels:{
	    			display: false
	    		}
	    	},
	    	scales:{
	    		xAxes:[{
	    			ticks: {
                    	max: 120
                	}
	    		}]
	    	},
	    	responsive: true,
	    	maintainAspectRatio: false
	    },

	});
</script>
{{< /rawhtml >}}

# Final thoughts

Distinguishing between photos and cg images can be pretty difficult. The result of only 58.67% accuracy for the non-3D-graphics-software users suggests that for the untrained eye it is basically impossible.

Regular users 3D-graphics-software got better results than participants that had never used 3D-graphics-software. It would be interesting to find out whether this is specific to 3D-graphics-software or applies to other visual/artistic tasks like painting.

Something that was not covered by this study is the resolution and size at which the images were shown. It is likely that part of the participants viewed the images on a small mobile device and part on a larger screen. It is possible (even likely) that this also influences the results.

The more time you spend with the data the more creative ideas come to mind. And there is a lot more to be discovered. 

After the survey had opened&nbsp;I started working on a machine learning model to distinguish photo from cg. While some initial results look promising there are still improvements to make. So stay tuned for the results of my neural network and a full comparison.

# Links

## The raw data

The data was collected between the October &nbsp;25th 2018 and January 16th 2019. It is licensed under the Open Database License with Attribution (ODC-By). For more information see the attached _license.txt_

Details about the schema can be found in _schema.txt_

The images are **not** part of the data-set and **not** licensed under ODC-By. Instead all rights belong to the respective authors. All images were used with permission.


	<a class="download-link" title="Version 1.0" href="https://oweissbarth.de/download/1352/" rel="nofollow"> Photo or CG Survey Raw data (348 downloads) </a> 

## Evaluation scripts

The scripts used to generate the above evaluations can be found  {{< new_tab "https://github.com/oweissbarth/photocgsurvey-evaluation" "here" >}}.

## Survey software

The software that was used to run the survey is custom and can be found {{< new_tab "https://github.com/oweissbarth/photoorcgsurvey" "here" >}}. This was developed more or less in a single day. It is very purpose-built (read hacky)



 {{< rawhtml >}}
 <style>
	.preview{
		width: 200px;
		height: 200px;
		cursor: pointer;
    max-width: none;
	}
	.survey_image{
		flex: 0;
		/*border: 1px solid ;*/
		box-shadow: 0 0 5px rgba(50, 50, 50, 0.5);
		padding: 1em;
		margin: 1em;
		position: relative;
	}
	.container{
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;

	}
	.correct_label{
		font-size: 1.5em;
		padding-bottom: 0.5em;
	}

	.credits{
		color: rgb(70,70,70);
		margin-bottom: 3.5em;
	}

	.average_accuracy{
		font-size: 2em;
		position: absolute;
		bottom: 1em;
	}
</style>
{{< /rawhtml >}}