<script>
  let source = "";
  
  // ======== GREAT! it works ================
  async function extractTag2(url = "") {
  	try {
  		source = await fetch(url);
  		if (!source.ok) throw new Error("those who are behind fail in real life");
  
  		let result = await source.text();
  		source = result;
  		console.log(source);
  
  	} catch (error) {
  		console.log(error);
  	}
  
  
  }

  function extractTag(url = "http://htmlpreview.github.io/?"){
    source = url + document.getElementById('url');
  }
  
  async function wait() {
  	await new Promise(resolve => setTimeout(resolve, 1000));
  
  }
  function displayHtmlFile() {
  	document.getElementById('displayAllHtmlHere').innerHTML =  `
      <iframe src="${source}">`
  }

  function doIt() {
    extractTag(document.getElementById('url').value);
    wait();
    displayHtmlFile();
  }
  
</script>

<label>Paste url here or click the links below</label><br>
<input id="url" type="text" value="https://github.com/lvsl123/my-pc/blob/main/css/button.html">

<br><br>
<button onclick="doIt()"> Display html page</button>

<div id="displayAllHtmlHere"></div>
