<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Website</title>
</head>
<body>
    <style>

* {
	padding: 0;
	margin: 0;
	box-sizing: border-box;
}
html {
	font-size: 10px;
	font-family: 'Montserrat', sans-serif;
	scroll-behavior: smooth;
}
a {
	text-decoration: none;
}
.container {
	min-height: 100vh;
	width: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
}
img {
	height: 100%;
	width: 100%;
	object-fit: cover;
}
p {
	color: black;
	font-size: 1.4rem;
	margin-top: 5px;
	line-height: 2.5rem;
	font-weight: 300;
	letter-spacing: 0.05rem;
}
.section-title {
	font-size: 4rem;
	font-weight: 300;
	color: black;
	margin-bottom: 10px;
	text-transform: uppercase;
	letter-spacing: 0.2rem;
	text-align: center;
}
.section-title span {
	color: crimson;
}

.cta {
	display: inline-block;
	padding: 10px 30px;
	color: white;
	background-color: transparent;
	border: 2px solid crimson;
	font-size: 2rem;
	text-transform: uppercase;
	letter-spacing: 0.1rem;
	margin-top: 30px;
	transition: 0.3s ease;
	transition-property: background-color, color;
}
.cta:hover {
	
	background-color: crimson;
	color: white;
}
.brand h1 {
	font-size: 3rem;
	text-transform: uppercase;
	color: white;
}
.brand h1 span {
	color: crimson;
}


#header {
	position: fixed;
	z-index: 1000;
	left: 0;
	top: 0;
	width: 100vw;
	height: auto;
}
#header .header {
	min-height: 8vh;
	background-color: rgba(31, 30, 30, 0.24);
	transition: 0.3s ease background-color;
}
#header .nav-bar {
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 100%;
	height: 100%;
	max-width: 1300px;
	padding: 0 10px;
}
#header .nav-list ul {
	list-style: none;
	position: absolute;
	background-color: rgb(31, 30, 30);
	width: 100vw;
	height: 100vh;
	left: 100%;
	top: 0;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	z-index: 1;
	overflow-x: hidden;
	transition: 0.5s ease left;
}
#header .nav-list ul.active {
	left: 0%;
}
#header .nav-list ul a {
	font-size: 2.5rem;
	font-weight: 500;
	letter-spacing: 0.2rem;
	text-decoration: none;
	color: white;
	text-transform: uppercase;
	padding: 20px;
	display: block;
}
#header .nav-list ul a::after {
	content: attr(data-after);
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%) scale(0);
	color: rgba(240, 248, 255, 0.021);
	font-size: 13rem;
	letter-spacing: 50px;
	z-index: -1;
	transition: 0.3s ease letter-spacing;
}
#header .nav-list ul li:hover a::after {
	transform: translate(-50%, -50%) scale(1);
	letter-spacing: initial;
}
#header .nav-list ul li:hover a {
	color: crimson;
}
#header .hamburger {
	height: 60px;
	width: 60px;
	display: inline-block;
	border: 3px solid white;
	border-radius: 50%;
	position: relative;
	display: flex;
	align-items: center;
	justify-content: center;
	z-index: 100;
	cursor: pointer;
	transform: scale(0.8);
	margin-right: 20px;
}

#header .hamburger:after {
	position: absolute;
	content: '';
	height: 100%;
	width: 100%;
	border-radius: 50%;
	border: 3px solid white;
	animation: hamburger_puls 1s ease infinite;
}
#header .hamburger .bar {
	height: 2px;
	width: 30px;
	position: relative;
	background-color: white;
	z-index: -1;
}
#header .hamburger .bar::after,
#header .hamburger .bar::before {
	content: '';
	position: absolute;
	height: 100%;
	width: 100%;
	left: 0;
	background-color: white;
	transition: 0.3s ease;
	transition-property: top, bottom;
}
#header .hamburger .bar::after {
	top: 8px;
}
#header .hamburger .bar::before {
	bottom: 8px;
}
#header .hamburger.active .bar::before {
	bottom: 0;
}
#header .hamburger.active .bar::after {
	top: 0;
}

#hero {
	background-image: url('images/10.jpg');
	background-size: cover;
	background-position: top center;
	position: relative;
	z-index: 1;
}
#hero::after {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-color: black;
	opacity: 0.7;
	z-index: -1;
}
#hero .hero {
	max-width: 1200px;
	margin: 0 auto;
	padding: 0 50px;
	justify-content: flex-start;
}
#hero h1 {
	display: block;
	width: fit-content;
	font-size: 4rem;
	position: relative;
	color: transparent;
	animation: text_reveal 0.5s ease forwards;
	animation-delay: 1s;
}
#hero h1:nth-child(1) {
	animation-delay: 1s;
}
#hero h1:nth-child(2) {
	animation-delay: 2s;
}
#hero h1:nth-child(3) {
	animation: text_reveal_name 0.5s ease forwards;
	animation-delay: 3s;
}
#hero h1 span {
	position: absolute;
	top: 0;
	left: 0;
	height: 100%;
	width: 0;
	background-color: crimson;
	animation: text_reveal_box 1s ease;
	animation-delay: 0.5s;
}
#hero h1:nth-child(1) span {
	animation-delay: 0.5s;
}
#hero h1:nth-child(2) span {
	animation-delay: 1.5s;
}
#hero h1:nth-child(3) span {
	animation-delay: 2.5s;
}


#services .services {
	flex-direction: column;
	text-align: center;
	max-width: 10px;
	margin: 0 auto;
	padding: 100px 0;
}
#services .service-top {
	padding: 150px 0px 0px 0px;
	max-width: 500px;
	margin: 0 auto;
}
#services .service-bottom {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-wrap: wrap;
	margin-top: 50px;
}
#services .service-item {
    flex-basis: 80%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 30px;
    border-radius: 10px;
    background-size: cover;
    margin: 10px 5%;
    position: relative;
    z-index: 1;
    overflow: visible; 
}

#services .service-item::after {
	content: 'left';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	opacity: 0.9;
	z-index: -1;
}
#services .service-bottom .icon {
	height: 80px;
	width: 80px;
	margin-bottom: 20px;

}
#services .service-item h2 {
	font-size: 2rem;
	color: white;
	margin-bottom: 10px;
	text-transform: uppercase;
}
#services .service-item p {
	color: white;
	text-align: left;
}

#projects .projects {
	flex-direction: column;
	max-width: 1200px;
	margin: 0 auto;
	padding: 100px 0;
}
#projects .projects-header h1 {
	margin-bottom: 50px;
}
#projects .all-projects {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
}
#projects .project-item {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
	width: 80%;
	margin: 20px auto;
	overflow: hidden;
	border-radius: 10px;
}
#projects .project-info {
	padding: 30px;
	flex-basis: 50%;
	height: 100%;
	display: flex;
	align-items: flex-start;
	justify-content: center;
	flex-direction: column;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	color: white;
}
#projects .project-info h1 {
	font-size: 4rem;
	font-weight: 500;
}
#projects .project-info h2 {
	font-size: 1.8rem;
	font-weight: 500;
	margin-top: 10px;
}
#projects .project-info p {
	color: white;
}
#projects .project-img {
	flex-basis: 50%;
	height: 200px;
	overflow: hidden;
	position: relative;
}
#projects .project-img:after {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	opacity: 0.7;
}
#projects .project-img img {
	transition: 0.3s ease transform;
}
#projects .project-item:hover .project-img img {
	transform: scale(1.1);
}

#about .about {
	flex-direction: column-reverse;
	text-align: center;
	max-width: 1200px;
	margin: 0 auto;
	padding: 100px 20px;
}
#about .col-left {
	width: 250px;
	height: 360px;
}
#about .col-right {
	width: 100%;
}
#about .col-right h2 {
	font-size: 1.8rem;
	font-weight: 500;
	letter-spacing: 0.2rem;
	margin-bottom: 10px;
}
#about .col-right p {
	margin-bottom: 20px;
}
#about .col-right .cta {
	color: black;
	margin-bottom: 50px;
	padding: 10px 20px;
	font-size: 2rem;
}
#about .col-left .about-img {
	height: 100%;
	width: 100%;
	position: relative;
	border: 10px solid white;
}
#about .col-left .about-img::after {
	content: '';
	position: absolute;
	left: -33px;
	top: 19px;
	height: 98%;
	width: 98%;
	border: 7px solid crimson;
	z-index: -1;
}
#contact .contact {
  flex-direction: column;
  max-width: 1200px;
  margin: 0 auto;
  width: 90%;
}

#contact .contact-items {
  width: 100%;
}

#contact .contact-item {
  width: 80%;
  margin: 30px auto;
  padding: 30px ;
  text-align: center;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  box-shadow: 0 0 18px 0 #0000002c;
  transition: 0.3s ease box-shadow;
}

#contact .contact-item:hover {
  box-shadow: 0 0 5px 0 #0000002c;
}

#contact .icon {
  width: 70px;
  margin-bottom: 10px;
  display: inline-block; 
}

#contact .contact-info h1 {
  font-size: 2.5rem;
  font-weight: 500;
  margin-bottom: 5px;
}

#contact .contact-info h2 {
  font-size: 1.3rem;
  line-height: 2rem;
  font-weight: 500;
}


#footer {
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
}
#footer .footer {
	min-height: 200px;
	flex-direction: column;
	padding-top: 50px;
	padding-bottom: 10px;
}
#footer h2 {
	color: white;
	font-weight: 500;
	font-size: 1.8rem;
	letter-spacing: 0.1rem;
	margin-top: 10px;
	margin-bottom: 10px;
}
#footer .social-icon {
	display: flex;
	margin-bottom: 30px;
}
#footer .social-item {
	height: 50px;
	width: 50px;
	margin: 0 5px;
}
#footer .social-item img {
	filter: grayscale(1);
	transition: 0.3s ease filter;
}
#footer .social-item:hover img {
	filter: grayscale(0);
}
#footer p {
	color: white;
	font-size: 1.3rem;
}

@keyframes hamburger_puls {
	0% {
		opacity: 1;
		transform: scale(1);
	}
	100% {
		opacity: 0;
		transform: scale(1.4);
	}
}
@keyframes text_reveal_box {
	50% {
		width: 100%;
		left: 0;
	}
	100% {
		width: 0;
		left: 100%;
	}
}
@keyframes text_reveal {
	100% {
		color: white;
	}
}
@keyframes text_reveal_name {
	100% {
		color: crimson;
		font-weight: 500;
	}
}

@media only screen and (min-width: 768px) {
	.cta {
		font-size: 2.5rem;
		padding: 20px 60px;
	}
	h1.section-title {
		font-size: 6rem;
	}

	#hero h1 {
		font-size: 7rem;
	}

	#services .service-bottom .service-item {
		flex-basis: 45%;
		margin: 2.5%;
	}
	
	#projects .project-item {
		flex-direction: row;
	}
	#projects .project-item:nth-child(even) {
		flex-direction: row-reverse;
	}
	#projects .project-item {
		height: 400px;
		margin: 0;
		width: 100%;
		border-radius: 0;
	}
	#projects .all-projects .project-info {
		height: 100%;
	}
	#projects .all-projects .project-img {
		height: 100%;
	}

	#about .about {
		flex-direction: row;
	}
	#about .col-left {
		width: 600px;
		height: 400px;
		padding-left: 60px;
	}
	#about .about .col-left .about-img::after {
		left: -45px;
		top: 34px;
		height: 98%;
		width: 98%;
		border: 10px solid crimson;
	}
	#about .col-right {
		text-align: left;
		padding: 30px;
	}
	#about .col-right h1 {
		text-align: left;
	}
	
	#contact .contact {
		flex-direction: column;
		padding: 100px 0;
		align-items: center;
		justify-content: center;
		min-width: 20vh;
	}
	#contact .contact-items {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		margin: 0;
	}
	#contact .contact-item {
		width: 30%;
		margin: 0;
		flex-direction: row;
	}
	#contact .contact-item .icon {
		height: 100px;
		width: 100px;
	}
	#contact .contact-item .icon img {
		object-fit: contain;
	}
	#contact .contact-item .contact-info {
		width: 100%;
		text-align: left;
		padding-left: 20px;
	}
	
}

@media only screen and (min-width: 1200px) {
	#header .hamburger {
		display: none;
	}
	#header .nav-list ul {
		position: initial;
		display: block;
		height: auto;
		width: fit-content;
		background-color: transparent;
	}
	#header .nav-list ul li {
		display: inline-block;
	}
	#header .nav-list ul li a {
		font-size: 1.8rem;
	}
	#header .nav-list ul a:after {
		display: none;
	}

	#services .service-bottom .service-item {
		flex-basis: 22%;
		margin: 1.5%;
	}
	.downloadbutton {
            display: inline-block;
            padding: 10px 30px;
            color: rgb(255, 255, 255);
            background-color: transparent;
            border: 2px solid crimson;
            font-size: 1rem;
            text-transform: uppercase;
            letter-spacing: 0.1rem;
            margin-top: 30px;
            transition: 0.3s ease;
            transition-property: background-color, color;
            width: 150px;
            height: 50px;
            text-align: center; 
            cursor: pointer; 
        }
		.downloadbutton:hover {
            background-color: crimson;
       
        }
      }
   </style>
  
  <section id="header">
    <div class="header container" >
      <div class="nav-bar">
        <div class="brand">
          <a href="#hero">
            <h1><span>E</span>ng.<span>A</span>land <span>B</span>akr</h1>
          </a>
        </div>
        <div class="nav-list"  >
          <div class="hamburger" >
            <div class="bar" ></div>
          </div>
          <ul>
            <li><a href="#hero" data-after="Home">Home</a></li>
            <li><a href="#services" data-after="Service">Services</a></li>
            <li><a href="#projects" data-after="Projects">Projects</a></li>
            <li><a href="#about" data-after="About">About</a></li>
            <li><a href="#contact" data-after="Contact">Contact</a></li>
          </ul>
        </div>
      </div>
    </div>
  </section>
 
  <section id="hero">
    <div class="hero container">
      <div>
        <h1>Hello, <span></span></h1>
        <h1>My Name is <span></span></h1>
        <h1>Aland <span></span></h1>
	</div>
    </div>
  </section>

  <section id="services">
 
      <div class="service-top">
        <h1 class="section-title">Serv<span>I</span>ces</h1>
        <p>In my career, I've consistently excelled in delivering diverse services, 
			specializing in effective project management, insightful data analysis, 
			and top-notch customer service. My skills extend to optimizing processes and enhancing efficiency.
			 Whether leading teams or collaborating, I'm dedicated to providing value and contributing to operational success.</p>
      </div>
      <div class="service-bottom">
        <div class="service-item">
          <div class="icon"><img src="images/11.png" /></div>
          <h2>Technical Skills</h2>
          <p> 
			I possess a robust and extensive set of technical skills in network management and administration, 
			reflecting a profound understanding and proficiency in overseeing the smooth functioning and security of intricate networking infrastructures.
			 My expertise encompasses a wide range of tasks and responsibilities,
			 ensuring the seamless operation, optimization, and protection of networks within diverse and dynamic environments.<br><br></p>
        </div>
        <div class="service-item">
          <div class="icon"><img src="images/12.png" /></div>
          <h2>Soft Skills</h2>
          <p>
			I'm skilled in creative problem-solving and innovative design thinking, with a knack for clear communication and effective collaboration.
			 I thrive in fast-paced environments, leading teams to deliver high-quality designs on time.
			  My approach is driven by empathy, resulting in solutions that deeply resonate with users.
			   I excel under pressure, consistently delivering exceptional design work with a focus on excellence.
			   <br><br></p>
        </div>
        <div class="service-item">
          <div class="icon"><img src="images/13.png" /></div>
          <h2>Certifications</h2>
          <p>
			I'm a third-stage Information System Engineering student with a focus on system architecture and software development.
			 I also hold a CCNA certificate, highlighting my expertise in Cisco networking, including device configuration and network security.
			 My combined academic and technical background positions me as a versatile professional in information systems and networking.<br><br><br><br></p>
       
        </div>
      </div>
    </div>
  </section>
  
  <section id="projects">
    <div class="projects container">
      <div class="projects-header">
        <h1 class="section-title">Recent <span>Projects</span></h1>
      </div>
      <div class="all-projects">
        <div class="project-item">
          <div class="project-info">
            <h1>Simple Connections</h1>
            <h2>networking engineer is love</h2>
            <p>Humanity and networks have a close connection that has changed over time.
				 From old ways of talking to today's internet and social media, how we communicate and connect has transformed a lot. 
				 for that i have a project are designed Simple Connections.</p>
				 <P>To See My Project Click At :</P>
				 <object type="application/x-pkt" data="C:\Users\sedrfgh\Desktop\portfolio\projects\Simple Connection.pkt" width="100%" height="600px">
                <a href="C:\Users\sedrfgh\Desktop\portfolio\projects\Simple Connection.pkt"> <button class="downloadbutton">Download</button> </a>
            </object>
          </div>
          <div class="project-img">
            <img  src="images/1.jpg" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Smart Home</h1>
            <h2>networking engineer is Love</h2>
            <p>In today's digital age, the smart home is a marvel of convenience and efficiency.
				 With a structured network comprising a server, wireless router, 
				 and various wireless devices like laptops, fans, lamps, doors, and garage doors, 
				we have unprecedented control over our environment. For that i have an Smart Home design</p>
				<P>To See My Project Click At :</P>
				<object type="application/x-pkt" data="C:\Users\sedrfgh\Desktop\portfolio\projects\SMART HOME.pkt" width="100%" height="600px">
                <a href="C:\Users\sedrfgh\Desktop\portfolio\projects\SMART HOME.pkt"> <button class="downloadbutton">Download</button> </a>
               </object>
			</div>
          <div class="project-img">
            <img src="images/2.jpg" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Telecommunication Architecture</h1>
            <h2>networking engineer is Love</h2>
            <p>Telecommunication is the lifeblood of our connected world, 
				seamlessly linking individuals and societies across vast distances. 
				At its core lies a sophisticated infrastructure comprising networks, 
				satellites, and devices, 
				all working in concert to facilitate communication.and there the big local telecommunication system</p>
				<P>To See My Project Click At :</P>
				<object type="application/x-pkt" data="C:\Users\sedrfgh\Desktop\portfolio\projects\Telecommunication Systems.pkt" width="100%" height="600px">
                <a href="C:\Users\sedrfgh\Desktop\portfolio\projects\Telecommunication Systems.pkt"><button class="downloadbutton">Download</button> </a>
               </object>
			  
          </div>
          <div class="project-img">
            <img src="images\3.jpg" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>College Network</h1>
            <h2>networking engineer is Love</h2>
            <p>Within the bustling hub of higher education,
				 the college network stands as the digital backbone,
				  fueling learning, collaboration, and innovation.
				   It comprises a sophisticated infrastructure of servers,
				    routers, switches, and wireless access points,
				 all meticulously designed to support the academic endeavors of students and faculty alike.</p>
				 <P>To See My Project Click At :</P>
			                <object type="application/x-pkt" data="C:\Users\sedrfgh\Desktop\portfolio\projects\College Network.pkt" width="100%" height="600px">
                <a href="C:\Users\sedrfgh\Desktop\portfolio\projects\College Network.pkt"> <button class="downloadbutton">Download</button> </a>
               </object>
          </div>
          <div class="project-img">
            <img src="images/4.jpg" alt="img">
          </div>
        </div>
       
        </div>
      </div>
    </div>
  </section>

  <section id="about">
    <div class="about container">
      <div class="col-left">
        <div class="about-img">
          <img src="images/5.jpg"  alt="img">
        </div>
      </div>
	  <div class="col-right">
		<h1 class="section-title">About <span>me</span></h1>
		<h2>Network Engineer</h2>
		<p>Hi there! I'm Aland Bakr Salam, 
			a network engineer with a knack for problem-solving and a passion for design engineering. 
			Currently studying at Erbil Polytechnic University, I'm all about hands-on learning. 
			From setting up networks to optimizing and securing them, I'm your go-to guy. 
			Check out my portfolio to see my projects and skills in action. 
			Let's connect and explore the exciting world of technology together! Thanks for stopping by!</p>
			
			<a href="images/Resume.pdf" download="My_Resume.pdf" class="cta">Show CV</a>
 <br><br>


      </div>
    </div>

  </section>
 
  <section id="contact">
	<div class="contact container">
	  <h1 class="section-title">Contact <span>info</span></h1>
	  <div class="contact-items">
		<div class="contact-item">
		  <div class="icon"><img src="images/6.png" /></div>
		  <div class="contact-info">
			<h1><b>Telegram</b></h1>
			<h2>07500806687</h2>
			<h2><u><a href="https://t.me/Aland_bakr_salam" target="_blank">Click at me</a></u></h2>
		  </div>
		</div>
		<div class="contact-item">
		  <div class="icon"><img src="images/7.png" /></div>
		  <div class="contact-info">
			<h1><b>Email</b></h1>
			<h2>thek99705@gmail.com</h2>
			<h2>alandbakr@gmail.com</h2>
		  </div>
		</div>
		<div class="contact-item">
		  <div class="icon"><img src="images/8.png" /></div>
		  <div class="contact-info">
			<h1><b>Calling</b></h1>
			<h2>07500806687</h2>
			<h2>07768974047*</h2>

		</div>
		</div>
	  </div>
	 </div>
  </section>
  
  


  <section id="footer">
    <div class="footer container">
      <div class="brand">
		<h1><span>E</span>ng.<span>A</span>land <span>B</span>akr</h1>
	</div>
      <h2>To see my content closely click on the buttom icon</h2>
      <div class="social-icon " id="1" >
        <div class="social-item">
			 <a  href="https://www.linkedin.com/in/eng-aland-bakr-6abb5a2b7/"><img src="images/9.png" /></a>
		 </div>
      </div>
    </div>
  </section>
 

  <script >
const hamburger = document.querySelector('.header .nav-bar .nav-list .hamburger');
const mobile_menu = document.querySelector('.header .nav-bar .nav-list ul');
const menu_item = document.querySelectorAll('.header .nav-bar .nav-list ul li a');
const header = document.querySelector('.header.container');

hamburger.addEventListener('click', () => {
	hamburger.classList.toggle('active');
	mobile_menu.classList.toggle('active');});

document.addEventListener('scroll', () => {
	var scroll_position = window.scrollY;
	if (scroll_position > 250) {
		header.style.backgroundColor = '#29323c';} else {
		header.style.backgroundColor = 'transparent';
	}});

menu_item.forEach((item) => {
	item.addEventListener('click', () => {
		hamburger.classList.toggle('active');
		mobile_menu.classList.toggle('active');
	});});
  </script>
</body>

</html>
