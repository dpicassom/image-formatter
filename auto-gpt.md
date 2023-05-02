# Role

write down a stand alone html file with html, css and js code to achieve the goals

# Goals

- Use interact js 
- Use vanilla js or bootstrap 5 only if needed or reduces the length of the code in 15% or more
- website must be responsive
- have the website:
    1. have a form where the user loads photo (raster image) files (can select multiple files at once)
    2. by submitting the form -the button says 'subir fotografías'-, a modal -wich spans the whole viewport- opens up, with the following characteristics:
        i. opens up initially with the first image 
        ii. Has the name of the image displayed as the title of the modal in its' header, yet it has an edit button to change it's name (it toogles the input tag from editable to non-editable).
        iii. In the footer of the modal there's two buttons, the first one says 'descartar' which deletes the current image from the uploaded files, and has a toamto color with whte text; and the 'aceptar button' which has a green color with white text
        iv. In the body of the modal, appears the current image, within a canvas tag, spanning the whole modal in either width or height, whatever is bigger.
        v. On top of the image there's a rectangle -named 'cropping tool'- with the following characteristics:
            a.  it's draggable and resizable
            b.  it's totally translucent with solid green borders
            c.  can only exist within the limits of the image (or the canvas, as the canvas must fit the image perfectly). Thus, the rectangle can only be dragged to a position if it allows it -with it's current dimensions- to exist within the canvas, otherwise it can't be dragged.
            d. it can be resized with the following constrains:
                1.  it must mantain a 800x600 widith:height ratio
                2.  it's minmum size should be 800x600 pixels of the displayed image. calculations must be done in order to calculate equivalent viewport pixels to the raster image pixels. The idea is that the rectangle is a croppig tool to standardize photos to a 800x600 aspect ratio and 800x600 pixels of raster image is the minimium we want to conserve. So even if the minimum viewport width and height is not 800x600 viewport pixels, it should represent 800x600 pixels of the current image at its minimum allowable size.
        vi. if they click the 'aceptar' button, the modal now:
            a.  displays a loading animation instead of the image
            b.  crops the image to the extent of the cropping-tool rectangle using the technoque explained in https://cloudinary.com/guides/automatic-image-cropping/cropping-images-in-javascript
            c. resizes the image to 800x600 pixels by using the technique explained in https://code.tutsplus.com/tutorials/how-to-crop-or-resize-an-image-with-javascript--cms-40446
            c. reformats that image into webp with only 10% loss using a js library.
            d. appends that image to the 'photo bar'
            e. once this is done, repolace the loading animation with the next uploade image or exit the modal if it was the last.
    3. Once they click submit, the form is reloaded/refreshed and now it says 'agrega más fotografías'. on top of it, the 'photo bar' appears, which displays miniviews of the edited photos as they are added from the modal. The photos can be selected, and if selected, a tomato colored delete button appears -but it says 'eliminar'-. Also none will be selected if there's any click outside the photo bar, thus the delete button would dissapear.