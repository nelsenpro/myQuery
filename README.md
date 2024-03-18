# myQuery
Membuat Library JavaScript Mirip jQuery untuk Manipulasi DOM (Document Object Model)
## Langkah-langkah untuk membuat Library JavaScript mirip jQuery untuk manipulasi DOM adalah sebagai berikut:
### 1. buat file myQuery.js dan Definisi Selector ($)
```javascript
function $(selector) {
    try {
        const self = {
            element: document.querySelector(selector),
        };
        return self;
    } catch (error) {
        console.error('Error in $ function:', error);
    }
}
```
### Menambah Method Pertama (html)
```javascript
html: function(value) {
    try {
        if (value === undefined) {
            return this.element.innerHTML;
        }
        this.element.innerHTML = value;
        return this;
    } catch (error) {
        console.error('Error in html method:', error);
    }
},
```
## Jadi Begini 
```javascript
function $(selector) {
    try {
        const self = {
            element: document.querySelector(selector),
            html: function(value) {
                try {
                    if (value === undefined) {
                        return this.element.innerHTML;
                    }
                    this.element.innerHTML = value;
                    return this;
                } catch (error) {
                    console.error('Error in html method:', error);
                }
            },
        };
        return self;
    } catch (error) {
        console.error('Error in $ function:', error);
    }
}
```
### contoh html
Hubungkan myQuery.js
```html
<!-- Memasukkan file JavaScript myQuery library -->
<script src="myQuery.js" type="text/javascript" charset="utf-8"></script>
```
Syntax Dasar
```html
$('#myDiv').html('New Content');
```
HTML 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Using $ Function</title>
    <!-- Memasukkan file JavaScript myQuery library -->
    <script src="myQuery.js" type="text/javascript" charset="utf-8"></script>
</head>
<body>
    <div id="myDiv">
        Konten Lama
    </div>
    <script>
        // Contoh penggunaan fungsi $ untuk mengubah konten HTML
        $('#myDiv').html('Konten Baru');
    </script>
</body>
</html>
```
### Menambah method ke dua (addClass)
```javascript
addClass: function(className) {
    try {
        if (className) {
            this.element.classList.add(className);
        }
        return this;
    } catch (error) {
        console.error('Error in addClass method:', error);
    }
},
```
### jadi begini 
```javascript
function $(selector) {
    try {
        const self = {
            element: document.querySelector(selector),
            html: function(value) {
                try {
                    if (value === undefined) {
                        return this.element.innerHTML;
                    }
                    this.element.innerHTML = value;
                    return this;
                } catch (error) {
                    console.error('Error in html method:', error);
                }
            },
            addClass: function(className) {
                try {
                    if (className) {
                        this.element.classList.add(className);
                    }
                    return this;
                } catch (error) {
                    console.error('Error in addClass method:', error);
                }
            },
            // tambahkan metode lainnya disini 
        };
        return self;
    } catch (error) {
        console.error('Error in $ function:', error);
    }
}
```
Syntax Dasar
```javascript
$('#contoh').addClass('kelasbaru');
```
HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh HTML dengan JavaScript</title>
    <style>
        .kelasbaru {
            background-color: yellow;
        }
    </style>
    <script src="myQuery.js" type="text/javascript" charset="utf-8"></script>
</head>
<body>
    <div id="contoh">
        Ini adalah sebuah div.
    </div>
    <script>
        // Panggil fungsi $ setelah semua elemen dimuat
        window.onload = function() {
            $('#contoh').addClass('kelasbaru');
        };
    </script>
</body>
</html>
```



