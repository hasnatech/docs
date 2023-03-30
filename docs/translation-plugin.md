# Translation Plugin

## Initialize code in index

    <script type="text/javascript" class="upperlayer">
        function googleTranslateElementInit() {
        docReady(() => {
            // console.log(document.getElementById("google_translate_element"))
            if (document.getElementById("google_translate_element") != null) {
            new google.translate.TranslateElement({
                pageLanguage: 'en',
                layout: google.translate.TranslateElement.InlineLayout.SIMPLE
            }, 'google_translate_element');
            } else {
            setTimeout(() => {
                googleTranslateElementInit();
            }, 1000)
            }
        })
        }
        function docReady(fn) {
        // see if DOM is already available
        if (document.readyState === "complete" || document.readyState === "interactive") {
            // call on next available tick
            setTimeout(fn, 1);
        } else {
            document.addEventListener("DOMContentLoaded", fn);
        }
        }

    </script>
    <script type="text/javascript"
        src="https://translate.google.com/translate_a/element.js?cb=googleTranslateElementInit">
    </script>


## CSS to remove labels

    .goog-te-gadget-icon,
    .skiptranslate iframe {
        display: none;
    }

## Add Div in HTML
    <div id="google_translate_element"></div>