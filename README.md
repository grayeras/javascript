var NS;
NS = {
                writeImageNumber :function();
                newImage         :function ();
                Nexter           :function();
                Backer           :function();
                currentIndex     :function();
                automaticly      :function();



     currentIndx=0;


    MyImages[7] = [ 'poza1.jpg', 'poza2.jpg', 'poza3.jpg', 'poza4.jpg', 'poza5.jpg', 'poza6.jpg', 'poza7.jpg'];
    Messages[7] = ['Coffee', 'Chocolate', 'Tee', 'Milk', 'Tee', 'Milk', 'Tee'];

   imagesPreloaded = new ArrayImages(7);


    for (var i = 0; i <this.MyImages.length; i++) {

       this.imagesPreloaded[i] = Image(350, 350);
       this.imagesPreloaded[i].src = this.MyImages[i]

    },
    function writeImageNumber() {
        this.oSpan = this.document.getElementById("sp1");

    },


    function newImage() {

// Makes a random, whole number between 0 and 3

        this.currentIndx = Math.round(Math.random() * 7);

        this.document.theImage.src = this.imagesPreloaded[currentIndx].src;

    },


    function Nexter() {
        if (this.currentIndx < this.imagesPreloaded.length - 1) {
           this.currentIndx = this.currentIndx + 1;
            this.document.theImage.src = this.imagesPreloaded[currentIndx].src;
            this.document.form1.text1.value = this.Messages[currentIndx];

        }
        else {
            this.currentIndx = 0;
            this.document.theImage.src = imagesPreloaded[currentIndx].src;
            this.document.form1.text1.value = Messages[currentIndx];

        }
        writeImageNumber();
    },


    function Backer() {
        if (currentIndx > 0) {
            this.currentIndx = this.currentIndx - 1;
            this.document.theImage.src = this.imagesPreloaded[currentIndx].src;
            this.document.form1.text1.value = this.Messages[currentIndx];
        }
        else {
            this.currentIndx = 3;
            this.document.theImage.src = this.imagesPreloaded[currentIndx].src;
            this.document.form1.text1.value = this.Messages[currentIndx];
        }
        writeImageNumber();
    },


    function setCurrentIndex() {
        this.currentIndx = 0;
        this.document.theImage.src = this.MyImages[0];
        this.document.form1.text1.value = this.Messages[0];
        writeImageNumber();
    },
    function automaticly() {
        if (document.form1.automatic.checked)
        {
            if (currentIndx < imagesPreloaded.length) {
                this.currentIndx = currentIndx;
            }
            else {
                this.currentIndx = 0;
            }
            writeImageNumber();
            this.document.theImage.src = this.imagesPreloaded[currentIndx].src;
            this.document.form1.text1.value = this.Messages[currentIndx];
            this.currentIndx = this.currentIndx + 1;
            var delay = setTimeout("automaticly()", 800);
        }
    },


}
