<script src="script.js"></script>
/* Toggle mobile menu */
function toggleMenu() {
    if (menu.classList.contains("active")) {
        menu.classList.remove("active");
         
        // adds the menu (hamburger) icon
        toggle.querySelector("a").innerHTML = "<i class=’fas fa-bars’></i>";
    } else {
        menu.classList.add("active");
         
        // adds the close (x) icon
        toggle.querySelector("a").innerHTML = "<i class=’fas fa-times’></i>";
    }
}
 
/* Event Listener */
toggle.addEventListener("click", toggleMenu, false);

/* Activate Submenu */
function toggleItem() {
  if (this.classList.contains("submenu-active")) {
    this.classList.remove("submenu-active");
  } else if (menu.querySelector(".submenu-active")) {
    menu.querySelector(".submenu-active").classList.remove("submenu-active");
    this.classList.add("submenu-active");
  } else {
    this.classList.add("submenu-active");
  }
}
 
/* Event Listeners */
for (let item of items) {
    if (item.querySelector(".submenu")) {
      item.addEventListener("click", toggleItem, false);
      item.addEventListener("keypress", toggleItem, false);
    }   
}

/* Tablet menu */
@media all and (min-width: 700px) {
    .menu {
        justify-content: center;
    }
    .logo {
        flex: 1;
    }
    .item.button {
        width: auto;
        order: 1;
        display: block;
    }
    .toggle {
        flex: 1;
        text-align: right;
        order: 2;
    }
    /* Button up from tablet screen */
    .menu li.button a {
        padding: 10px 15px;
        margin: 5px 0;
    }
    .button a {
        background: #0080ff;
        border: 1px royalblue solid;
    }
    .button.secondary {
        border: 0;
    }
    .button.secondary a {
        background: transparent;
        border: 1px #0080ff solid;  
    }
    .button a:hover {
        text-decoration: none;
    }
    .button:not(.secondary) a:hover {
        background: royalblue;
        border-color: darkblue;
    }
}
<html>
<head>
   
<style type="text/css">
#navegador ul{
   list-style-type: none;
   text-align: center;
}
#navegador li{
   display: inline;
   text-align: center;
   margin: 0 10px 0 0;
}
#navegador li a {
   padding: 4px 14px 4px 14px;
   color: #267CB9;
   background-color: #eeeeee;
   border: 1px solid #ccc;
   text-decoration: none;
}
#navegador li a:hover{
   background-color: #333333;
   color: #ffffff;
}
   </style>
</head>

<body>


<div id="navegador">
<ul>
<li><a href="http://ags.aarongs.org/">Inicio</a></li>
<li><a href="https://AaronGS1999.github.io/aarongs.github.io/Trayectoria.html">Trayectoria</a></li>
<li><a href="https://AaronGS1999.github.io/aarongs.github.io/Publicaciones.html">Publicaciones</a></li>
</ul>
</div>
  
 /* Mobile menu */
.menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
}
.menu li a {
    display: block;
    padding: 15px 5px;
}
.menu li.subitem a {
    padding: 15px;
}
.toggle {
    order: 1;
    font-size: 20px;
}
.item.button {
    order: 2;
}
.item {
    order: 3;
    width: 100%;
    text-align: center;
    display: none;
}
.active .item {
    display: block;
}
.button.secondary { /* divider between buttons and menu links */
    border-bottom: 1px #444 solid;
}
  
 /* Submenu up from mobile screens */
.submenu {
    display: none;
}
.submenu-active .submenu {
   display: block;
}
.has-submenu i {
    font-size: 12px;
}
.has-submenu > a::after {
    font-family: "Font Awesome 5 Free";
    font-size: 12px;
    line-height: 16px;
    font-weight: 900; 
    content: "\f078";
    color: white;
    padding-left: 5px;
}
.subitem a {
    padding: 10px 15px;
}
.submenu-active {
    background-color: #111;
    border-radius: 3px;
}
/* Tablet menu */
@media all and (min-width: 700px) {
    .menu {
        justify-content: center;
    }
    .logo {
        flex: 1;
    }
    .item.button {
        width: auto;
        order: 1;
        display: block;
    }
    .toggle {
        flex: 1;
        text-align: right;
        order: 2;
    }
    /* Button up from tablet screen */
    .menu li.button a {
        padding: 10px 15px;
        margin: 5px 0;
    }
    .button a {
        background: #0080ff;
        border: 1px royalblue solid;
    }
    .button.secondary {
        border: 0;
    }
    .button.secondary a {
        background: transparent;
        border: 1px #0080ff solid;  
    }
    .button a:hover {
        text-decoration: none;
    }
    .button:not(.secondary) a:hover {
        background: royalblue;
        border-color: darkblue;
    }
}
 
/* Desktop menu */
@media all and (min-width: 960px) {
    .menu {
        align-items: flex-start;     
        flex-wrap: nowrap;
        background: none;
    }
    .logo {
        order: 0;
    }
    .item {
        order: 1;
        position: relative;
        display: block; 
        width: auto;
    }
    .button {
        order: 2;
    }
    .submenu-active .submenu {
        display: block;
        position: absolute;
        left: 0;
        top: 68px;
        background: #111;
    }
    .toggle {
        display: none;
    }
    .submenu-active {
        border-radius: 0;
    }
}
  
</body>
</html>

/* Close Submenu From Anywhere */
function closeSubmenu(e) {
  if (menu.querySelector(".submenu-active")) {
    let isClickInside = menu
      .querySelector(".submenu-active")
      .contains(e.target);
 
    if (!isClickInside && menu.querySelector(".submenu-active")) {
      menu.querySelector(".submenu-active").classList.remove("submenu-active");
    }
  }
}
 
/* Event listener */
document.addEventListener("click", closeSubmenu, false);

