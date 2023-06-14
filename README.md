# Exam
exam repo

 <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        .main {
            width: 70%;
            height: 500px;
            margin: auto;
            margin-top: 100px;
            border: 1px;
            position: relative;
            box-shadow: 0px 0px 10px gray;
            overflow: hidden;
        }

        .slide {
            height: 100%;
            width: 100%;
            position: absolute;
        }

        .slides {
            display: flex;
            height: 100%;
            width: 100%;
        }

        .nav {
            text-align: center;
            margin-top: 15px;
        }

        .nav button {
            font-size: 20px;
            padding: 5px;
        }
        .slide{
            display: none;
        }
        .active{
            display: block;
        }
    </style>
</head>

<body>
    <div class="main">
        <div class="slides">
            <img src="img.jpg" alt="img1" class="slide active">
            <img src="img2.jpg" alt="img2" class="slide">
            <img src="img3.jpg" alt="img3" class="slide">
        </div>
    </div>
    <div class="nav">
        <button id="prev">Prev</button>
        <button id="next">Next</button>
    </div>

</body>
<script>
    let currentindex = 0;
   
        const slide = document.querySelectorAll("img");
        const prevButton = document.getElementById("prev");
        const nextButton = document.getElementById("next");
       
       function nextslide() {
        slide[currentindex].classList.remove("active");
        currentindex++;
        if (currentindex >= slide.length) {
            currentindex = 0;
        }
        slide[currentindex].classList.add("active");
       }

       function previouslide() {
        slide[currentindex].classList.remove("active");
        currentindex--;
        if (currentindex < 0) {
            currentindex = slide.length - 1;
        }
        slide[currentindex].classList.add("active");
       }

       nextButton.addEventListener("click",nextslide);
       prevButton.addEventListener("click",previouslide);

       slide[currentindex].classList.add("active");

       setInterval(nextslide,3000);
</script>
