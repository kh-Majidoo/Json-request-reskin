// === vars
  // request
  var btn = document.getElementById('btn');
  var btn2 = document.getElementById('btn2');
  var search = document.getElementById('inputHolder');
  var container = document.getElementById('container');
  var myData =[];
  var i =0;

  //themes
  const darkButton = document.getElementById('dark');
  const lightButton = document.getElementById('light');
  const dArrow = document.getElementById('dArrow');

  const body = document.body;

  var headerCol= document.getElementById('header-col');
  var themeClr = document.getElementsByClassName('themeClr');
  var dropdown = document.getElementsByClassName('dropdown');
  var currColor ;



  //local Storage
  const theme = localStorage.getItem('theme');
  const color = localStorage.getItem('color');

 //====listeners

  window.onload=sendRequest();
  search.addEventListener('keyup',filterNames);



  //Functions
  function sendRequest(){
      var request= new XMLHttpRequest();
      request.open('GET','http://www.filltext.com/?rows=30&First_name={firstName}&Last_name={lastName}&tel={phone|format}&city={city}&address={streetAddress}}&zip={zip}&pretty=true');
      request.onload=function(){
        myData = JSON.parse(request.responseText);
      };
      request.send();
    };
  function renderUser(data){
    currColor = headerCol.classList[1];
            var userString = "";
            userString+= `<ul class="userLi themeClr ${currColor}">
                          <li class="nameClass">${data[i].First_name}.</li>
                          <li>${data[i].Last_name}.</li>
                          <li>${data[i].tel}</li>
                          <li>${data[i].city}.</li>
                          <li>${data[i].address}.</li>
                          <li class="zip">${data[i].zip}</li></ul>`
            container.insertAdjacentHTML('beforeend',userString);
            i++;

            if(i>=data.length){
              btn.classList.add('ded_btn');
              btn2.classList.add('ded_btn');
            }
  }
  function renderUsers(data){
    currColor = headerCol.classList[1];
            var userString = "";
            for (i ; i< data.length ;i++){
            userString +=`<ul class="userLi themeClr ${currColor}">
                          <li class="nameClass">${data[i].First_name}.</li>
                          <li>${data[i].Last_name}.</li>
                          <li>${data[i].tel}</li>
                          <li>${data[i].city}.</li>
                          <li>${data[i].address}.</li>
                          <li class="zip">${data[i].zip}</li></ul>`
            }
            container.insertAdjacentHTML('beforeend',userString);

            if(i==data.length){
              btn.classList.add('ded_btn');
              btn2.classList.add('ded_btn');
          }
        }
  function filterNames(){
      var names = document.getElementsByClassName("nameClass");
      let filterValue = search.value.toUpperCase();

      for (i = 0; i < names.length; i++) {
        a = names[i];
        if(a.innerHTML.toUpperCase().indexOf(filterValue) > -1){
          a.parentElement.style.display='flex';
        }
        else{
          a.parentElement.style.display='none';
        }
      }
    }





  //====local storage
    if (theme) {
    body.classList.remove('light','dark');
     body.classList.add(theme);
    }
    if(color) {
      for (var i = 0; i < themeClr.length; i++) {
        themeClr[i].classList.add(color);
      }
    }
//Themes
    darkButton.onclick = () => {
      body.classList.replace('light','dark');
      localStorage.setItem('theme','dark');
    };
    lightButton.onclick = () => {
      body.classList.replace('dark','light');
      localStorage.setItem('theme','light');
    };
//Colors
    water.onclick = () => {
        for (var i = 0; i < themeClr.length; i++) {
          themeClr[i].classList.remove('fire', 'leaf');
          themeClr[i].classList.add('water');
        }
        localStorage.setItem('color','water');
      }
    fire.onclick = () => {
        for (var i = 0; i < themeClr.length; i++) {
          themeClr[i].classList.remove('water', 'leaf');
          themeClr[i].classList.add('fire');
        }
        localStorage.setItem('color','fire');
      }
    leaf.onclick = () => {
        for (var i = 0; i < themeClr.length; i++) {
          themeClr[i].classList.remove('water', 'fire');
          themeClr[i].classList.add('leaf');
        }
        localStorage.setItem('color','leaf');
      }

    dArrow.onclick = () => {
      var euh = dropdown[0].classList.contains('hidden')
      for (var i = 0; i < dropdown.length; i++) {
        if (euh) {
          dropdown[i].classList.remove('hidden');
        }else{
        dropdown[i].classList.add('hidden');
      }
    }
  }
