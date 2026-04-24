<script>
  let source = "";
  // async // ======== GREAT! it works ================
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
  
  extractTag("https://raw.githubusercontent.com/lvsl123/my-pc/refs/heads/main/css/button.html");wait();displayHtmlFile();
  
</script>

<div id="displayAllHtmlHere">   </div>
