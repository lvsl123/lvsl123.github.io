<script>
  // async // ======== GREAT! it works ================
  async function extractTagNotInUse() {
  	try {
  		source = await fetch("./print-this.html");
  		if (!source.ok) throw new Error("those who are behind fail in real life");
  
  		let result = await source.text();
  		source = result;
  		console.log(source);
  
  	} catch (error) {
  		console.log(error);
  	}
  
  
  }
extractTag();
</script>

