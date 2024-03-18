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
```javascript
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
        $.ready(function() {
            $('#contoh').addClass('kelasbaru');
        )};
    </script>
</body>
</html>
```
## myQuery.js
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
            on: function(event, callback) {
                try {
                    this.element.addEventListener(event, callback);
                    return this;
                } catch (error) {
                    console.error('Error in on method:', error);
                }
            },
            append: function(elements) {
                try {
                    elements.forEach(element => {
                        this.element.appendChild(element);
                    });
                    return this;
                } catch (error) {
                    console.error('Error in append method:', error);
                }
            },
            css: function(styles) {
                try {
                    Object.assign(this.element.style, styles);
                    return this;
                } catch (error) {
                    console.error('Error in css method:', error);
                }
            },
            hide: function() {
                try {
                    this.element.style.display = 'none';
                    return this;
                } catch (error) {
                    console.error('Error in hide method:', error);
                }
            },
            show: function() {
                try {
                    this.element.style.display = '';
                    return this;
                } catch (error) {
                    console.error('Error in show method:', error);
                }
            },
            remove: function() {
                try {
                    this.element.parentNode.removeChild(this.element);
                    return this;
                } catch (error) {
                    console.error('Error in remove method:', error);
                }
            },
            attr: function(name, value) {
                try {
                    if (value === undefined) {
                        return this.element.getAttribute(name);
                    }
                    this.element.setAttribute(name, value);
                    return this;
                } catch (error) {
                    console.error('Error in attr method:', error);
                }
            },
            animate: function(keyframes, options) {
                try {
                    this.element.animate(keyframes, options);
                    return this;
                } catch (error) {
                    console.error('Error in animate method:', error);
                }
            },
            fadeIn: function(duration) {
                try {
                    this.element.style.transition = `opacity ${duration / 1000}s ease`;
                    this.element.style.opacity = '1';
                    return this;
                } catch (error) {
                    console.error('Error in fadeIn method:', error);
                }
            },
            fadeOut: function(duration) {
                try {
                    this.element.style.transition = `opacity ${duration / 1000}s ease`;
                    this.element.style.opacity = '0';
                    return this;
                } catch (error) {
                    console.error('Error in fadeOut method:', error);
                }
            },
            toggle: function() {
                try {
                    if (this.element.style.display === 'none') {
                        this.show();
                    } else {
                        this.hide();
                    }
                    return this;
                } catch (error) {
                    console.error('Error in toggle method:', error);
                }
            },
            val: function(value) {
                try {
                    if (value === undefined) {
                        return this.element.value;
                    }
                    this.element.value = value;
                    return this;
                } catch (error) {
                    console.error('Error in val method:', error);
                }
            },
            text: function(value) {
                try {
                    if (value === undefined) {
                        return this.element.textContent;
                    }
                    this.element.textContent = value;
                    return this;
                } catch(error) {
                    console.error('Error in text method:', error);
                }
            },
            width: function() {
                try {
                    return this.element.offsetWidth;
                } catch (error) {
                    console.error('Error in width method:', error);
                }
            },
            height: function() {
                try {
                    return this.element.offsetHeight;
                } catch (error) {
                    console.error('Error in height method:', error);
                }
            },
        };
        return self;
    } catch (error) {
        console.error('Error in $ function:', error);
    }
}

$.ready = function(callback) {
    if (document.readyState !== 'loading') {
        callback();
    } else {
        document.addEventListener('DOMContentLoaded', callback);
    }
};
```
## Contoh penggunaan $(document).ready()
Syntax Dasar 
```javascript
$.ready(function() {});
```
cara menggunakan :: Setelah Dokumen di muat, jalankan fungsi 
```javascript
$.ready(function() {
    $('#myDiv').html('New Content');
});
```
```javascript
$.ready(function() {
    $('#contoh').addClass('kelasbaru');
});
```
###### Mencoba Myqr.js sebuah Library Javascript mirip JQuery 
[Coba Myqr.js](https://github.com/nelsenpro/myqr)
###### Mencoba CodeCanvas.js sebuah Runtime.js, memungkinkan kamu menulis css dan javascript dalam tag <cc>...</cc>
[Coba CC.js](https://github.com/nelsenpro/cc)
#### Author by Nelsen Niko 
