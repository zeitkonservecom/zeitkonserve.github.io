```
CSS:

/* tablets and phones */
@media only screen and (max-width: 1024px) and (min-width: 768px) {
    #device {
        height: 2px;
    }
}
/* phone, overrides the above */
@media only screen and (max-width: 767px) {
    #device {
        height: 1px;
    }
}

HTML:

<div id="device" style="display:none"></div>

or TypoScript (insert in Root-Template):

page.17 = TEXT
page.17.value (
<div id="device" style="display:none"></div>
)

Javascript:

function phone() {
    return $("#device").css("height").indexOf("1px") !== -1;
}

function tablet() {
    return $("#device").css("height").indexOf("2px") !== -1;
}

function desktop() {
    return $("#device").css("height").indexOf("3px") !== -1;
}



```
