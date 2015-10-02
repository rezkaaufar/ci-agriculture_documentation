IFM File Upload
===========================

Steps:
---------------------------------------------------------------------------
1. Send request to get upload url to this endpoint:
	GET http://192.168.10.188:9000/farmer/upload/getUrl/
	params:
		farmer_id:String -> id of the farmer
		file_info:String -> meta of the image file, i.e. 'profile_picture'
	response:
		- 200
			{
				"upload_url": "xxx"
			}
		- 500
			internal error
2. Send multipart/form request to upload file to file storage service, i.e. "xxx"
	POST xxx
	headers:
		Content-Type: multipart/form-data; boundary=Nonce
	body:
		image: <to-be-uploaded-file>

	response:
		- 200
			{
				"public_url": "yyy"
			}
		- 500
			internal error
3. Use public url to access the file image directly
---------------------------------------------------------------------------

Each farmer might have several files. The information of farmer's files url can be accessed with
	GET http://192.168.10.188:9000/farmer/files/path
	params:
		farmer_id:String -> id of the farmer
	response:
		- 200
			{
				"<file_info>": "<file_public_url>"
				[
					{
						file_info: "profile",
						file_url: url
					}
				]
			}