<script>
	import Hero from "$components/helpers/Hero.svelte";
	import DemoScrolly from "$components/demo/Demo.Scrolly.svelte";
	import Image from "$components/helpers/Image.svelte";
	import Video from "$components/helpers/Video.svelte";
	/*import { autoType, autoType } from "d3";*/
	import Shoheicard from '$svg/card_Shohei.svg';
    import Sotocard from '$svg/card_Soto.svg';
    import Marcocard from '$svg/card_Marco.svg';
    import Zachcard from '$svg/card_Zach.svg';
	let choice = $state("AVG")
			  $inspect({choice})
	import {onMount} from "svelte";
	import stadiumSvg from '$svg/stadium_final.svg';
	import { autoType } from "d3";
		let hoveredId = $state() // stores the id of the rectangle that's being hovered on
    	// This is a JavaScript Object
    	// salaries["Aaron Judge"] -> 40M
    	const salaries = {
        	"Juan Soto": '61.875M',
        	"Zach Wheeler": '42M',
       	 	"Aaron Judge": '40M',
       	 	"Jacob deGrom": '40M',
        	"Anthony Rendon": '38.57M',
        	"Carlos Correa": '37.33M',
       		"Jose Altuve": '33M',
        	"Tyler Glasnow": '32.5M',
        	"Nolan Arenado": '32M',
        	"Corbin Burnes": '30.83M',
        	"Vladimir Guerrero Jr.": '28.5M',
        	"Dansby Swanson": '28M',
        	"Rafael Devers": '28M',
        	"Kris Bryant": '27M',
        	"Xander Bogaerts": '25.45M',
        	"Matt Chapman": '25.16M',
        	"Jack Flaherty": '25M',
        	"Luis Castillo": '24.15M',
        	"Christian Yelich": '24.09M',
        	"Austin Riley": '22M',
        	"Nick Martinez": '21.05M',
        	"Luis Severino": '20M',
        	"Salvador Perez": '20M',
        	"Jose Ramirez": '19M',
        	"Zach Eflin": '18M',
       		"Sandy Alcantara": '17.3M',
        	"Andrew Benintendi": '17.1M',
        	"Mitch Keller": '15.41M',
        	"Ha-seong Kim": '13M',
        	"Nathaniel Lowe": '10.3M'
    	};
    	onMount(() => {
   			const rectangles = Array.from(document.querySelectorAll("rect, path")).filter(d => !d.id.startsWith("Rectangle") && !d.id.startsWith("Vector"));
    		console.log({rectangles})
    		rectangles.forEach(rectangle => {
    		rectangle.addEventListener("mouseenter", (e) =>
    	{hoveredId = e.target.id;});
    		rectangle.addEventListener("mouseleave", (e) =>
    	{hoveredId = undefined;})})
    	});

</script>

<div id="demo">
	<Hero
	src="assets/images/mbcover.svg"
	alt="Is Moneyball Dead?"
/>
<section>
	<div class="text">
		<p>Baseball has remained a sustainable sport for many reasons, 
			and while it would be nice if it were as simple as the catchy 
			tune about going to the ballpark, grabbing some Cracker Jack, 
			and shouting "Three strikes, you're out," the reality is that 
			baseball is a business. And over the past few decades, money 
			has been changing the game.</p>

		<p>
			In 2023, Shohei Ohtani entered into free agency after playing 
			six years with the Los Angeles Angels. The offseason brought 
			spirited speculation over where he would sign.
		</p>

		<p>
			It was no surprise that the 2018 Rookie of the Year, two-time 
			American League MVP, two-time Silver Slugger award winner and 
			five-time All-MLB First Team recipient was highly pursued by 
			several teams – and everyone was ready to put a big check on 
			the table. 
		</p>
	
			<Image
				src="assets/images/shoheiawards.svg"
				alt="Shohei Awards 2018-2023"
			/>

		<p>
			Several teams were rumored to be in the Ohtani sweepstakes. However, 
			experts believe that one team stood out above all the rest: the 
			Los Angeles Dodgers. 		</p>

		<p>
			Regardless of the rumors, it was clear that becoming a World 
			Series Champion was a top priority for Ohtani. So the question 
			was, which team would give him the best shot of getting there?
		</p>
		<p>
			After about a month of quiet negotiations, Ohtani took to his Instagram 
			to announce the news: 		</p>

		<p>
			He had signed a record-breaking contract of $700 million with the 
			Los Angeles Dodgers. 
		</p>
		<p>
			This was the highest contract ever signed in MLB history. Previously, the 
			record was held by Ohtani’s former teammate, Mike Trout, who signed a 
			12-year $426.5 million contract with the Los Angeles Angels in 2019. </p>
		<p>
			The deal worked out between the Dodgers and Ohtani was for 10 years 
			with a $680 million deferral of payment until the contract was up, 
			which ESPN reported was Ohtani’s idea. This means that his annual 
			salary will be $2 million until 2034, and then $68 million annually 
			for the 10 years after that. </p>
		<p>
			It is not surprising that throughout MLB history, the big-name teams 
			land the big-name players. However, this contract made it obvious 
			that in the business of baseball, a canyon was forming between the 
			smallest-market teams and the largest.  </p>
		<p>
			The 2024 season resulted in a World Series between the two historic 
			MLB tycoons: the Los Angeles Dodgers and the New York Yankees. The 
			Los Angeles Dodgers would go on to win, making Ohtani a World Series 
			champion in his first season with the team.   </p>
		<p> 
			Then, into the offseason this past December, something shocking happened. </p>
		<p> 
			Free agent Juan Soto and the New York Mets surpassed Ohtani’s contract 
			with a deal of $765 million for 15 years and no deferral of payment, 
			deeming Soto the new record-holder.  </p>
	</div>
	
	<style>
	.cards_container{
        display: flex;
		align-items: center;
        width: 100%;
        height: auto;
        padding: auto;
        max-width: 200px;
    }
	</style>

<div class="row">
	<div class="cards_container">
        {@html Shoheicard}
    </div>
    <div class="cards_container">
        {@html Sotocard}
    </div>
    <div class="cards_container">
        {@html Marcocard}
    </div>
    <div class="cards_container">
        {@html Zachcard}
    </div>
</div>
	<!--div class="row">
			<Image
				src="assets/images/card_Shohei.svg"
				alt="Shohei Ohtani" />
			<Image
				src="assets/images/card_Soto.svg"
				alt="Juan Soto" />
			<Image
				src="assets/images/card_Marco.svg"
				alt="Marco Gonzales" />
			<Image
				src="assets/images/card_Zach.svg"
				alt="Zach Eflin" />-->
		<style>
			.row{max-width: 60rem; padding: 16px; margin: 0 auto;}
		</style>
	</div>
	<div class="caption">
		The baseball cards above display the contracts of the Shohei Ohtani, 
		Juan Soto, Marco Gonzales and Zach Eflin, who are all the highest paid 
		players on their respective teams. Ohtani and Soto belong to teams whose 
		total payroll is among the highest in the league, while Gonzales and 
		Eflin belong to teams among the lowest payrolls. Source: Spotrac.com
	</div>

	<div class="chart-wrapper">
		<iframe title="There is a maximum $5M million gap between the highest-paid players 
		on each team." aria-label="Bar Chart" id="datawrapper-chart-VTTNq" 
		src="https://datawrapper.dwcdn.net/VTTNq/1/" scrolling="no" frameborder="0" 
		style="width: 0; margin: 0 auto; padding: 32px; min-width: 100% !important; border: none;" 
		height="900" data-external="1"></iframe>
		<p style="font-size:x-small; text-align:center">Note: Shohei Ohtani does not appear on this chart because of the deferral of payment
			that was agreed to in his contract.
		</p>
	</div>

	<!--<div class="caption">
		 
	</div>-->
<div class="row">
	<div class="stadium-container">
        {@html stadiumSvg}
		<style>
			.stadium-container{
				align: center;
			}
		</style>
    </div>
</div>
    <div class="name-salary">
    	{#if hoveredId}
        	<p>Player: {hoveredId}</p>
        	<p>Salary: {salaries[hoveredId]}</p>
    	{/if}
    </div>


<section>
	
	<main>
		<div class="text">
			<p>The Moneyball Philosophy</p>
		</div>
		<div style="text-align: center">
		<iframe width="840" height="472.5" 
			src="https://www.youtube.com/embed/Tzin1DgexlE?si=t9ID64CrUcHnNPc4&amp;start=88" 
			title="YouTube video player" 
			frameborder="0" 
			allow="accelerometer; autoplay; 
			clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
			referrerpolicy="strict-origin-when-cross-origin" allowfullscreen
			style="margin: 0 auto; justify-content: center; align-items: center;"
		></iframe>
		</div>
	</main>
	
	<div class="text">
		<p>
			For several decades after the MLB’s inception in 1903, the best players 
			regularly ended up with the wealthiest teams. However, in 1965, the 
			league held its first-ever draft which gave an opportunity to 
			bottom-feeder teams to acquire better talent. </p>
		<p>
			This raised new questions for baseball front offices to deliberate 
			when deciding who to draft. While this improved organizations’ chances 
			at adding the best amateur players to their rosters, it didn’t solve 
			the money issue. And as for free agents, wealthier teams still had 
			better luck signing star players. </p>
		<p> 
			So how does scouting work? </p>
		<p>
			The traditional scouting theory relies on scouts evaluating players 
			based on physical abilities like speed, arm strength, and hitting, 
			without focusing on statistics. Scouts assess mechanics and assign grades 
			to players, emphasizing tools like agility, arm motion and bat speed. </p>
		<p>
			This was the dominant strategy utilized until the Oakland Athletics and 
			its general manager Billy Beane shifted focus from traditional scouting 
			to advanced data and statistics in what became known as the moneyball 
			philosophy. </p>
		<p> 
			Following the loss to the New York Yankees in the 2001 playoffs and the 
			loss of three star players, Beane got to work. Operating with a smaller 
			budget than most of the league, the A’s couldn’t compete financially with 
			other teams when acquiring new talent, so Beane realized he had to 
			outsmart—not outspend—his competition. </p>
	<div class="img">
		<Image
			src="assets/images/beanequote.png"
			alt="Billy Beane Quote from Moneyball (2011)"
			/>
	</div>
		<p>
			Beane and his front office, including assistant general manager Paul 
			DePodesta, turned to sabermetrics—a data-driven approach to evaluating 
			players' performance. </p>
		<p> 
			Inspired by the work of economist Bill James, sabermetrics challenged 
			conventional wisdom in baseball by focusing on advanced statistics that 
			better correlate to a player’s contribution to winning games. </p>
		<p>
			The key metrics, particularly on-base percentage (OBP) and slugging 
			percentage (SLG), were used to uncover undervalued players who could 
			contribute to the team’s success while not costing the organization big 
			bucks. The strategy was revolutionary because it disregarded traditional 
			scouting and physical traits in favor of numbers that more accurately 
			predicted a player’s value. </p>
		<p>
			“This data-driven approach enabled the A’s to build a competitive team 
			despite their financial constraints, setting records for consecutive wins 
			— seven AL Western Division titles and 10 playoff appearances — and proving 
			that data analytics could level the playing field in professional sports,” 
			wrote Business Magazine. </p>
		<p>
			The success of Billy Beane and the Oakland A’s proved the power of the 
			moneyball philosophy, and because of this, the strategy changed the way 
			teams scout their players. </p>
		<p>
			“As analysts have transitioned to baseball’s front offices, sabermetric 
			thinking has exerted a noticeable impact on how the sport is played,” wrote 
			Matt Kelly, former MLB reporter and researcher who now manages multimedia 
			content at MLB. </p>
		<p> 
			However, now that the use of sabermetrics is a common practice throughout 
			the league, it no longer has the same competitive edge for small-market teams.</p>
	</div>
	</section>

<section>
		
		<main>
			<div class="text">
				<p>A Growing Disparity</p>
			</div>
		</main>
<div class="text">
	<p>
		Since the Oakland A’s had its odds-defying season in 2002, the economic 
		disparity between teams has only grown wider. </p>
	<p> 
		In 2024, there was an over $200 million gap between the New York Mets, 
		who had the highest payroll, and the Oakland A’s, who had the lowest. </p>
	<p>
		The average payroll (in millions) of all 30 MLB teams are shown in the chart below.
		To explore total payroll by year, click on the drop down menu to select 
		specific seasons. </p>
</div>
<div class="row">
	<div class="wrapper">
		<select name="payroll years" bind:value={choice}>
			<!--<option value="">choose</option>-->
			<option value="AVG">AVG</option>
			<option value="2024">2024</option>
			<option value="2023">2023</option>
			<option value="2022">2022</option>
			<option value="2021">2021</option>
			<option value="2020">2020</option>
			<option value="2019">2019</option>
			<option value="2018">2018</option>
			<option value="2017">2017</option>
			<option value="2016">2016</option>
			<option value="2015">2015</option>
			<option value="2014">2014</option>
			<option value="2013">2013</option>
		</select>
		<div class="row">
		  <div class="wrapper">
			{#if choice === "AVG"}
			<iframe title="On average, LAD's total payroll is the highest in 2013-2024" 
			aria-label="Bar Chart" id="datawrapper-chart-BcGUF" 
			src="https://datawrapper.dwcdn.net/BcGUF/2/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" 
			height="795" data-external="1"></iframe>
			{/if}
			{#if choice === "2024"}
			<iframe
				title="MLB Teams Payroll Ranking in 2024"
				aria-label="Bar Chart" id="datawrapper-chart-qkd9h"
				src="https://datawrapper.dwcdn.net/qkd9h/1/"
				scrolling="no" frameborder="0"
				style="width: 0; min-width: 100% !important; border: none;"
				height="785" data-external="1"></iframe>
	  		{/if}
	 		{#if choice === "2023"}
			<iframe title="MLB Teams Payroll Ranking in 2023"
				aria-label="Bar Chart" id="datawrapper-chart-Zgkrj"
				src="https://datawrapper.dwcdn.net/Zgkrj/1/"
				scrolling="no" frameborder="0"
				style="width: 0; min-width: 100% !important; border: none;"
				height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2022"}
			<iframe title="MLB Teams Payroll Ranking in 2022" 
			aria-label="Bar Chart" id="datawrapper-chart-BehxC" 
			src="https://datawrapper.dwcdn.net/BehxC/1/" scrolling="no" 
			frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="785" 
			data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2021"}
			<iframe title="MLB Teams Payroll Ranking in 2021" aria-label="Bar Chart" 
			id="datawrapper-chart-uANrr" src="https://datawrapper.dwcdn.net/uANrr/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2020"}
			<iframe title="MLB Teams Payroll Ranking in 2020" aria-label="Bar Chart" 
			id="datawrapper-chart-hS4E6" src="https://datawrapper.dwcdn.net/hS4E6/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2019"}
			<iframe title="MLB Teams Payroll Ranking in 2019" aria-label="Bar Chart" 
			id="datawrapper-chart-GmvVS" src="https://datawrapper.dwcdn.net/GmvVS/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2018"}
			<iframe title="MLB Teams Payroll Ranking in 2018" aria-label="Bar Chart" 
			id="datawrapper-chart-GSZXs" src="https://datawrapper.dwcdn.net/GSZXs/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	 		 {#if choice === "2017"}
			<iframe title="MLB Teams Payroll Ranking in 2017" aria-label="Bar Chart" 
			id="datawrapper-chart-Gf6XK" src="https://datawrapper.dwcdn.net/Gf6XK/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2016"}
			<iframe title="MLB Teams Payroll Ranking in 2016" aria-label="Bar Chart" 
			id="datawrapper-chart-KV3mj" src="https://datawrapper.dwcdn.net/KV3mj/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2015"}
			<iframe title="MLB Teams Payroll Ranking in 2015" aria-label="Bar Chart" 
			id="datawrapper-chart-tElI4" src="https://datawrapper.dwcdn.net/tElI4/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2014"}
			<iframe title="MLB Teams Payroll Ranking in 2014" aria-label="Bar Chart" 
			id="datawrapper-chart-jMwJF" src="https://datawrapper.dwcdn.net/jMwJF/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  		{#if choice === "2013"}
			<iframe title="MLB Teams Payroll Ranking in 2013" aria-label="Bar Chart" 
			id="datawrapper-chart-JdcpT" src="https://datawrapper.dwcdn.net/JdcpT/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="785" data-external="1"></iframe>
	  		{/if}
	  	</div>
	 	 <div class="wrapper">
			<iframe title="Total Playoff Appearance" aria-label="Bar Chart" 
			id="datawrapper-chart-sJEgW" src="https://datawrapper.dwcdn.net/sJEgW/1/" 
			scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; 
			border: none;" height="884" data-external="1"></iframe>
	 	 </div>
	<style>
		.row{display: flex; gap: two elements;grid-column-gap:37px;padding: 10px;width: 100%;}
	</style>
		</div>
	<style>
		.small{
			max-width: 60rem;
			padding: 16px;
			margin: 0 auto;
			font-size: small;
			position: relative;
			top: -75px;
		}
	</style>
	</div>	
</div>
		
		<div class="medium">
			<p>
				In the chart on the right, teams appear on the y-axis from highest average payroll over 
				the last 12 seasons at the top, to the lowest payrolls at the bottom. Playoff 
				bracket appearances were calculated based on the number of times a team appeared in a wild card, 
				divisional, or championship series and if they made it to the World Series. 
				Because higher-seeded teams start in the divisional series, rather than the 
				wildcard, a point was added to a team’s total number of appearances every 
				time it started its postseason run in the divisional. This was to ensure 
				that all teams at the divisional bracket level would have an equal number of total 
				appearances. For example, in 2024, the Dodgers, Yankees, Phillies and Guardians 
				received two points for their divisional appearances because they did not play in 
				a wildcard game. Whereas, the Padres, Mets, Royals and Tigers received one point 
				for a wildcard appearance and one point for a divisional appearance.</p>
			<p>
				In the last 12 seasons, the top 15 wealthiest teams appeared in 118 
				more playoff bracket appearances than the bottom 15. While every team 
				across the payroll spectrum made it to the playoffs at least once 
				since 2013, a noticeable dominance in appearances by the Dodgers, Mets, 
				Yankees, Astros and Braves is observed. This is partially because the 
				weighted calculation of playoff bracket appearances takes into account 
				how far teams make it in the playoffs. Both the Dodgers and the Astros 
				have made it to four World Series since 2013 and won twice. </p>

			<p>
				This shows that money had consistent influence on success. </p>
	
		<div class="row">
			<Image src="assets/images/winperscatter.png" alt text="Win Per vs. Average Salary Scatterplot"/>
			<Image src="assets/images/playoffscatter.png" alt text="Playoff Bracket Appearance vs. Average Salaray Scatterplot"/>
			<style>
				.row{
					padding: 5px;
				}
			</style>
		</div>
			<p> 
				Trends show that as average payroll increases, so does average win 
				percentage during the regular season. The same trend emerged for total 
				playoff bracket appearances. </p>
			<p>
				Additionally, since 2013, 11 out of 12 World Series winners were in the 
				upper half of payrolls when they won, while six of those 11 were in the 
				top 20%. </p>
			<p> 
				The Houston Astros were the only team in the last 12 seasons to win a 
				World Series while ranking in the bottom half of payrolls. The team won 
				its first-ever title in 2017 and ranked 13th in payroll that year. 
				However, two years later, reporters Ken Rosenthal and Evan Drellich 
				published an investigation in The Athletic exposing the Astros for using 
				cameras to illegally steal signs from opponents in the 2017 season. </p>
			<Video 
				src="assets/video/psteams13-24.mp4"
				alt="Post Season Teams 2013-2024"
				controls={false}
				customControls={true}
				/>
		<style>
			.medium{
				max-width: 60rem;
				padding: 16px;
				margin: 0 auto;
				position: relative;
				top: -50px;
			}
		</style>
		</div>
	</section>

	<section>
			
		<main>
			<div class="text">
				<p>The Salary Cap Debate</p>
			</div>
		</main>
			
		<div class="text">
			<p>
				There has been lively debate over what should be done about the payroll 
				gap between sports writers, MLB officials, team owners and fans alike. </p>
			<p>
				Implementing a salary cap, like those of the National Football League 
				and National Basketball League, have been a large piece of the 
				conversation, but hasn’t come without controversy.  </p>
			<p> 
				Contentious negotiations between the MLB and the Players Association 
				have ensued in recent years about the adoption of a league-wide salary 
				cap. The Players Association, or MLBPA, is the labor union that serves 
				as the bargaining agent for major and minor league players. The union 
				has consistently opposed the implementation of a salary cap, saying a 
				free-market allows players to maximize their value, according to 
				Bleacher Report. </p>
			<p>
				During a recent spring training media event, MLB commissioner Rob Manfred 
				said that the economic disparity in the sport is at the top of his list 
				of concerns, emphasizing that the system needs changing. </p>
			<p>
				The current collective bargaining agreement between the MLB and MLBPA 
				doesn’t expire until Dec. 2026, so until then, new negotiations of a 
				salary cap will have to wait. </p>
			<p> 
				In the meantime, the league has created a competitive balance tax, also 
				known as a luxury tax, which regulates the total amount of money teams 
				can spend on their rosters, according to MLB. </p>
			<p>
				Last year, the payroll threshold was set to $241 million which meant the 
				Dodgers, Mets, Yankees, Phillies, Braves, Rangers, Astros, Giants and 
				Cubs were taxed a specific percentage, according to ESPN.  </p>
			</div>
	</section>

	<section>
			
		<main>
			<div class="text">
				<p>A Sport of Luck</p>
			</div>
		</main>
					
		<div class="text">
			<p>
				Baseball is not an exact science, and as much as talent and money helps, 
				magic can happen. </p>
			<p>
				"You've seen teams with low payrolls win, and teams with high payrolls 
				lose, but those big markets have an advantage," Andrew Benintendi, 
				Chicago White Sox left fielder, said to ESPN.  </p>
			<p> 
				Contentious negotiations between the MLB and the Players Association 
				have ensued in recent years about the adoption of a league-wide salary 
				cap. The Players Association, or MLBPA, is the labor union that serves 
				as the bargaining agent for major and minor league players. The union 
				has consistently opposed the implementation of a salary cap, saying a 
				free-market allows players to maximize their value, according to 
				Bleacher Report. </p>
			<p>
				The Tampa Bay Rays, Cleveland Guardians and Arizona Diamondbacks have 
				all made it to the World Series once in the last nine seasons with some 
				of the smallest operating budgets – which is far better than the Los 
				Angeles Angels, who have one of the highest payrolls, can say.  </p>
			<p>
				So with Opening Day quickly approaching at the end of this month, could 
				an unforeseen underdog get lucky this season?  </p>
		</div>
	<div class="baseball8">
		<Image 
			src="assets/images/baseball9.png"
			alt="Baseball Magic 8 Ball"/>
	</div>
	</section>

<footer>
	<p>
		This is a project by students at the UC Berkeley Graduate School of
		Journalism
	</p>
</footer>

<style>
	.text {
		max-width: 60rem;
		padding: 16px;
		margin: 0 auto;
	}

	section {
		margin-top: 0 auto;
		margin-bottom: 0 auto;
		padding-top: 32px;
	}
	main {
		max-width: 60rem;
		margin-top: 2px auto;
		margin-bottom: 2px auto;
		margin: 0 auto;
		padding: 0 auto;
		font-weight: bold;
		font-size: xx-large;
	}
	.row{
		display: flex;
	}
	.column{
		flex: 50%;
		padding: 5px;
	}
	.chart-wrapper {
		width: 800px;
		margin: 0 auto;
	}
	.wrapper {
		width: 1200px;
		margin: 0 auto;
		margin-bottom: 0%;
		gap: 2 elements;
	}
	.cards_container{
        display: inline-block;
        width: 100%;
        height: auto;
        padding: auto;
        max-width: 200px;
    }
    .name-salary {
        display: inline-block;
        border-radius: 5px;
        height: 150px;
		text-align:center;
    } 
	.caption{
			max-width: 60rem;
			padding: 16px;
			margin: 0 auto;
			font-size: x-small;
			position: relative;
	}
	.stadium-container {
        display: inline-block;
        width: 100%;
        height: auto;
        max-width: 700px;
        overflow: hidden;
        margin: 0 auto;
    }
    .name-salary {
        display: block;
        margin: 10px 30px;
        border-radius: 5px;
        height: 150px;
    }
	img {
		width: 50%;
		height: 50%;
	}
	footer {
		background: var(--color-gray-800);
		color: white;
		padding: 1rem;
		text-align: center;
	}
	.baseball8 {
		width: 960px;
		height: 540px;
		margin: 0 auto;
	}
</style>
