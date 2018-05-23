<html>
	<head>
		<title>Search Table Sort</title>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1">
		<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
		<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
		<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.1/jquery.min.js" type="text/javascript"></script>
		<script src="http://ajax.aspnetcdn.com/ajax/jquery.validate/1.9/jquery.validate.min.js" type="text/javascript"></script>
		<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
		<script src="js/form-validation.js"></script>
		<script>
			function myFunction() {
				var x = document.getElementById("mySelectSort").value;
				if(x=="bookType"){
					sortSelect('#bookType', 'text', 'asc');
				}
				else if(x=="pageNo"){
					sortSelect('#pageNo', 'text', 'asc');
				}
				else{
					
				}
			}
			
			var sortSelect = function (select, attr, order) {
				if(attr === 'text'){
					if(order === 'asc'){
						$(select).html($(select).children('option').sort(function (x, y) {
							return $(x).text().toUpperCase() < $(y).text().toUpperCase() ? -1 : 1;
						}));
						$(select).get(0).selectedIndex = 0;
						e.preventDefault();
					}// end asc
					if(order === 'desc'){
						$(select).html($(select).children('option').sort(function (y, x) {
						return $(x).text().toUpperCase() < $(y).text().toUpperCase() ? -1 : 1;
					}));
					$(select).get(0).selectedIndex = 0;
					e.preventDefault();
					}// end desc
				}
			};
</script>
	</head>
	<style>
		body{
			border-style:double;
			border-color:black;
			background-color:white;
			border-width: thick;
			border-width: 3px;
		}
		.boxed {
			border: 1px solid black ;
			background-color:lightgrey;
			height: 150px;
			left:10px;
			margin: 3px;
		}
		.tab {
			overflow: hidden;
			background-color: black;
			border-top-left-radius: 5px;
			border-top-right-radius: 5px; 
			border-bottom-left-radius: 5px;
			border-bottom-right-radius: 5px; 
		}
		.tab button {
			background-color: grey;
			float: none;
			border-color:black;
			outline: none;
			cursor: pointer;
			padding: 15px 133px;
			transition: 0.9s;			
		}
		.tab button:hover {
			background-color: #ddd;
		}
		hr{
			border-color:grey;
		}
		#vertical{
			height: 320px;
			border-left: 3px solid black;
			position: absolute;
			top: 5px;
			left: 250px;
			text-align:center;
		}
		.boxed1 {
			border-top: 1px solid black ;
			background-color:lightgrey;
			height: 40px;
			left:5px;
			margin: 10px;
		}
		.previous {
			background-color: black;
			color: grey;
		}

		.next {
			background-color: black;
			color: grey;
		}
		#a {
			text-decoration: none;
			display: inline-block;
			padding: 5px 30px;
		}
		.panel-primary {
			color: #333;
			background-color: lightgrey;
			border-color:black;
		}
		.nav{
			color: #333;
			background-color: blue;
			border-color:red;
		}
	</style>
	<body>
		<div class="container-fluid">
			<div class="row">
				<div class="panel panel-primary">
					<div class="row">
						<div class="col-sm-12">
							<ul class="nav nav-tabs nav-justified" style="background-color:lightblue;">
								<li><a href="#"><b><font color="white" size="3px">All Books</font></b></a></li>
								<li><a href="#"><b><font color="black" size="3px">Books & E Books</font></b></a></li>
								<li><a href="#"><b><font color="white" size="3px">Magazine & Journals</font></b></a></li>
								<li><a href="#"><b><font color="white" size="3px">Media</font></b></a></li>
							  </ul>
						</div>
					</div>
					<br>
					<div class="row">
						<div class="col-sm-1">
						</div>
						<div class="col-sm-8">
							<input type="text" name="searchBar" placeholder="Search" style="background-color:lightgrey;width:950px;height:30px;border-color:grey;"/>
						</div>
						<div class="col-sm-3">
						&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
							<button type="submit" class="searchButton" style="background-color:green;width:100px;height:30px"><font color="white"><b>Search</b></font></button>
						</div>
					</div>
					<br>
					<div  class="row">
						<div class="col-sm-1">
						</div>
						<div class="col-sm-11">
							<u><a href="#">Advanced Search</a></u>
						</div>
					</div>
				</div>
			</div>
			<div class="row">
				<hr>
			</div>
			<div>
				<div class="row">
					<div class="col-sm-2">
						<font color="black" size="3px"><b>Search result</b></font>
					</div>
				</div>
				<br>
				<div class="row">
					<div class="col-sm-6 text-left">
						<a href="#" ><font color="blue">&laquo; Previous</font></a> |
						<a href="#" ><font color="blue">Next &raquo;</font></a>
					</div>
					<div class="col-sm-6 text-right">
						<select id="bookType" style="background-color:lightgrey">
							<option value="default">Select any item</option>
							<option value="Science">Science</option>
							<option value="History">History</option>
							<option value="Math">Math</option>
							<option value="Science fiction">Science fiction</option>
							<option value="Satire">Satire</option>
							<option value="Drama">Drama</option>
							<option value="Action and Adventure">Action and Adventure</option>
							<option value="Romance">Romance</option>
							<option value="Mystery">Mystery</option>
							<option value="Horror">Horror</option>
							<option value="Health">Health</option>
							<option value="Guide">Guide</option>
							<option value="Travel">Travel</option>
							<option value="Children's">Children's</option>
							<option value="Religion, Spirituality & New Age">Religion, Spirituality & New Age</option>
							<option value="Anthology">Anthology</option>
							<option value="Poetry">Poetry</option>
							<option value="Encyclopedias">Encyclopedias</option>
							<option value="Dictionaries">Dictionaries</option>
							<option value="Comics">Comics</option>
							<option value="Art">Art</option>
							<option value="Journals">Journals</option>
							<option value="Prayer books">Prayer books</option>
							<option value="Biographies">Biographies</option>
							<option value="Autobiographies">Autobiographies</option>
							<option value="Fantasy">Fantasy</option>
						</select >
						<select id="pageNo" style="background-color:lightgrey">
							<option value="default">Select any option</option>
							<option value="100">100 Per Page</option>
							<option value="200">200 Per Page</option>
							<option value="300">300 Per Page</option>
							<option value="400">400 Per Page</option>
						</select >
						<select id="mySelectSort" onchange="myFunction()" style="background-color:lightgrey">
							<option value="default">Sort</option>
							<option value="pageNo">Page Number</option>
							<option value="bookType">Book Type</option>
						</select>
					</div>
				</div>
			</div>
			<div class="row">
				<div class="boxed1">
					<div class="col-sm-2 text-center">
					</div>
					<div class="col-sm-7 text-center">
						<font color="black" size="3px"><b>Description</b></font>
					</div>
					<div class="col-sm-2 text-right">
						<font color="black" size="3px"><b>Select</b></font>
					</div>
				</div>
			</div>
			<div class = "row">
				<div class="col-sm-2 text-center">
					<img src="https://www.booktopia.com.au/http_coversbooktopiacomau/600/9781118469590/handbook-of-agricultural-entomology.jpg" style="height:60px;width:60px;"/>
				</div>
				<div class="col-sm-7 text-left">
					<font color="black" size="3px"><b>1. <i>Handbook of Agricultural Entomology </i>by Helmut van Emden</b></font><br>
					<font color="black" size="3px"><b>Language: English</b></font><br>
					<font color="black" size="3px"><b>Publisher: New York: [Time-Life Books], [1969-1970]</b></font>
				</div>
				<div class="col-sm-2 text-right">
					<input type="checkbox" id= "checkBox1" style="height:20px;width:20px;">
				</div>
			</div><br>
			<div class = "row">
				<div class="col-sm-2 text-center">
					<img src="https://i.ebayimg.com/images/g/xZ0AAOSw8AhaQ~U8/s-l300.jpg"  style="height:60px;width:60px;"></img>
				</div>
				<div class="col-sm-7 text-left">
					<font color="black" size="3px"><b>2.<i> Wild about books </i>by Judy Sierra; Marc Tolon Brown</b></font><br>
					<font color="black" size="3px"><b>Language: English</b></font><br>
					<font color="black" size="3px"><b>Publisher: New York: Alfred A. Knopf, 2004.</b></font>
				</div>
				<div class="col-sm-2 text-right">
					<input type="checkbox" id= "checkBox2"style="height:20px;width:20px;">
				</div>
			</div><br>
			<div class = "row">
				<div class="col-sm-2 text-center">
					<img src="https://cf.ltkcdn.net/business/images/std/30919-314x382-Books.jpg"  style="height:60px;width:60px;"></img>
				</div>
				<div class="col-sm-7 text-left">
					<font color="black" size="3px"><b>3. <i>The purchase of books</i> by public libraries by Great Britian.</b></font><br>
					<font color="black" size="3px"><b>Language: English</b></font><br>
					<font color="black" size="3px"><b>Publisher: London, H.M. Stationery Off., 1972.</b></font>
				</div>
				<div class="col-sm-2 text-right">
					<input type="checkbox" id= "checkBox3" checked="checked" style="height:20px;width:20px;"><br><br>
					<b><u><a href="#">Read</a>|<a href="#">Download</a></></b>
				</div>
			</div><br>	
			<div class = "row">			
				<div class="col-sm-11 text-right">
					<button type="submit" class="cancelButton" style="background-color:red;width:100px;height:30px"><font color="white"><b>Cancel</b></font></button>
					<button type="submit" class="reserveButton" style="background-color:blue;width:100px;height:30px"><font color="white"><b>Reserve</font></button>
				</div>
			</div>
			<div class="row">
				<div class="row">
					<div class="col-sm-2 text-center">
						<font color="black"><b>Speaker Notes</b></font>
					</div>
				</div>
				<br>
				<div class="row">
					<div class="col-sm-2 text-right">					
						<br><a href="#" id="a" class="previous">&laquo; Previous</font></a>
					</div>
					

					<div class="col-sm-2 ">
						<img src="https://3.bp.blogspot.com/-nWFQOMITbsQ/TaUlwWMqRtI/AAAAAAAAAfA/uXiFqh69Wzw/s80/sunrise.png"  style="height:60px;width:40%;"></img>
						<u><font color="black"><i> "Handbook of Agricultural Entomology" </i>by Helmut van Emden is a landmark publication for students</b></font></u>
					</div>

					<div class="col-sm-3 ">
						<img src="http://digital-storytime.com//graphics/DS_Logo.png"  style="height:60px;width:60%;"></img>
						<u><font color="black"><b>"This whimsical storyline is one that kids will love and identify with too, since young children are often as hard on their books as any monkey in the zoo!"</b></font></u>
					</div>
					
					<div class="col-sm-2 ">
						<img src="https://www.scribendi.com/images/cms/thumbnails/How-to-Write-a-Report-on-a-Book_100x100.jpg"  style="height:60px;width:60%;"></img>
						<u><font color="black"><b>"Historical fiction is mostly smoke and mirrors"</b></font></u>
					</div>

					<div class="col-sm-2 text-left">
						<br><a href="#" id="a" class="next"><font size="3px">Next &raquo;</a>
					</div>
				</div>
			</div>
		</div>
	</body>
</html>
