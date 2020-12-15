# Detect Labels, Faces, and Landmarks in Images with the Cloud Vision API

## Create an API Key API
Since you'll be using curl to send a request to the Vision API, you'll need to generate an API key to pass in your request URL.

**1. Untuk membuat kunci API, buka API & layanan > Kredensial di konsol Cloud Anda:**
*![apikey](https://cdn.qwiklabs.com/8cDO0kBoc2byO7otbM1QFWuYWv0ZZAUH1iBDR200dKA%3D)*

**2. Click on the Create credentials button. **
*![credentials](https://cdn.qwiklabs.com/OPRnwJAzyxcK1bvJ1Iv7f3FyL5WaNzAqwiu5Yr6oPTI%3D)*

**3. In the drop-down menu, select API key. **
*![dropdown](https://cdn.qwiklabs.com/OyE7y6jsqa%2BB6obwA%2BVYClGCPXy6ER1BKE0f3cLlx7s%3D)*

**4. Next, copy the key you just generated **

Now save it to an environment variable to avoid having to insert the value of your API key in each request.

Run the following in Cloud Shell, replacing <your_api_key> with the key you just copied:

**export API_KEY=<YOUR_API_KEY>**

## Upload an Image to a Cloud Storage bucket
There are two ways to send an image to the Vision API for image detection: by sending the API a base64 encoded image string, or passing it the URL of a file stored in Cloud Storage. We'll be using a Cloud Storage URL. The first step is to create a Cloud Storage bucket to store our images.

**1. Navigate to Navigation menu > Storage in the Cloud console for your project, then click Create bucket. **
*![bucked](https://cdn.qwiklabs.com/YjeT9%2FI0vbVTm8jEKjpWvL2yQdCuNCqQTnfTf%2Fsabmg%3D)*

**2. Give your bucket a unique name. You can use the default settings for the bucket - click Create. **
*![namebucked](https://cdn.qwiklabs.com/z%2FofyjLlIzROfsVasYRvkyP0ai5aN4I3HlY1LnmCViw%3D)*

**Upload an image to your bucket **

**1. Right click on the following image of donuts, then click Save image as and save it to your computer as donuts.png. **
*![testbucked](https://cdn.qwiklabs.com/V4PmEUI7yXdKpytLNRqwV%2ByGHqym%2BfhdktVi8nj4pPs%3D)*

**2. Go to the bucket you just created and click Upload files. Then select donuts.png. **
*![buckeddata](https://cdn.qwiklabs.com/Yh4DAGGG5sWsKdgvuVv8mhLb%2Fsr5hMb0OFOji7Wskm8%3D)*

**3. Now you need to make this image publicly available. Click on the 3 dots for your image and select Edit Permissions. **
*![edit](https://cdn.qwiklabs.com/kwtkEJ18%2FGOgDZs915lfQ4ZQvfnPbw8JkECN6egxmKg%3D)*

**4. Click Add entry then enter the following:**
*Entity: Public *

*Name: allUsers*

*Access: Reader*

*![entry](https://cdn.qwiklabs.com/5opGKCZNOra%2Bvgco3BPvDHr31iLHtzyIODmD65s7Jls%3D)*

**5. Then click Save. **
Now that you have the file in your bucket, you're ready to create a Vision API request, passing it the URL of this donuts picture.

## Create your Vision API request
Now you'll create a request.json file in the Cloud Shell environment.

**1. Using the Cloud Shell code editor (by clicking the pencil icon in the Cloud Shell ribbon). **
*![edit1](https://cdn.qwiklabs.com/O1pSCpaSe6p5nxOMmjQg3Vsf0YwHaqW2bT56hM6Iym0%3D)*

or your preferred command line editor (nano, vim, or emacs), create a request.json file.

**2. Type or paste the following code into the file:**
*![edit2](https://cdn.qwiklabs.com/O1pSCpaSe6p5nxOMmjQg3Vsf0YwHaqW2bT56hM6Iym0%3D)*

**Note:** Replace `my-bucket-name` with the name of your storage bucket.

{
  "requests": [
      {
        "image": {
          "source": {
              "gcsImageUri": "gs://my-bucket-name/donuts.png"
          }
        },
        "features": [
          {
            "type": "LABEL_DETECTION",
            "maxResults": 10
          }
        ]
      }
  ]
}


