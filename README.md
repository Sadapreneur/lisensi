var license = document.querySelector('#HTML99 .license-code').innerText;
var password = 'XXXXX';
var url = window.location.origin;
var code = btoa(license + '#' + password + '#' + url);
var oReq = new XMLHttpRequest();
oReq.addEventListener("load", function(){
  var hasil = JSON.parse(this.responseText);
  if (hasil['valid']) {
    return true;
  } else {
    window.location.href = 'https://www.sadapreneur.com';
  }
});
oReq.open("GET", "https://script.google.com/macros/s/AKfycbzLfAeFst0RHmjCQ2wJc0cLacWJE3sHYA3Leg65AzoRdXkFHKu5/exec?check="+code);
oReq.send();
} catch (e) {
window.location.href = 'https://www.sadapreneur.com';
}
}();
