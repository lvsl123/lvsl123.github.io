<script>
  let source = "";
  
  // ======== GREAT! it works ================
  async function extractTag(url = "") {
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
  
  async function wait() {
  	await new Promise(resolve => setTimeout(resolve, 1000));
  
  }
  function displayHtmlFile() {
  	document.getElementById('displayAllHtmlHere').innerHTML = source;
  }

  function doIt() {
    extractTag(document.getElementById('url').value);
    wait();
    displayHtmlFile();
  }
  
</script>

<label>Paste url here or click the links below</label><br>
<input id="url" type="text" value="https://raw.githubusercontent.com/lvsl123/my-pc/refs/heads/main/css/button.html"></input>

<br><br>
<button onclick="doIt()"> Display html page</button>

<div id="displayAllHtmlHere">  display all html here </div>
