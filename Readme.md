
# How to upload files without page refresh

# Html page code

    <form id="formaUp" method="post" enctype="multipart/form-data"  target="iframeUpload">
                      <input type="file" name="file" id="file" class="form-control" placeholder="Upload Image" >
                                  <input class="btn btn-white px-2" type="submit" id="upload-button" value="upload" onclick="uploadFile()"/>
                                  <iframe id="iframeUpload" name="iframeUpload" style="display:none"></iframe>
                              </form>
 # Script code
 
     function uploadFile(){
      var fileName = getFileName(document.getElementById('file').value);
      if(validateExtension(fileName)){
        var fileUploadForm = document.getElementById('formaUp');
        fileUploadForm.setAttribute("action", "upload");

		//fileName
		var optFileName = document.createElement("input");
		optFileName.type = "hidden";
		optFileName.value = fileName;
		optFileName.name = "fileName";
		fileUploadForm.appendChild(optFileName);

		document.getElementById('formaUp').submit();
		
		return fileName;
	}
	
	
	
}
