<!DOCTYPE html>
<html>
    <head>
        <style>
            input{box-sizing: border-box; position: absolute}
            output{display: block; text-align: center}
        </style>
        <script>
            function createElement(conStrElementTypeName, conStrParentId = document.getElementById("form")) {
                return conStrParentId.appendChild(document.createElement(conStrElementTypeName))
            }

            function createNumberInputElementTogetherWithItsLabelElementAndSetTheirPrpertiesOfInterest(conLblFirstNumber, conTxtFirstNumber, 
            conIntUnitlessWidthOfTextBox) {
                conLblFirstNumber[0] = createElement("label")
                conTxtFirstNumber[0] = createElement("input")
                conLblFirstNumber[0].innerHTML = "First Number"
                conLblFirstNumber[0].style.width = "auto"
                conLblFirstNumber[0].style.textWrap = "nowrap"
                conLblFirstNumber[0].style.position = "absolute"
                conTxtFirstNumber[0].style.width = conIntUnitlessWidthOfTextBox + "px"
            }

            function computeSum() {
                const conIntUnitlessWidthOfTextBox = 38
                const conFrmForm = createElement("form", document.getElementById("body"))
                conFrmForm.setAttribute("id", "form")
                const conLblFirstNumber = new Array(), conTxtFirstNumber = new Array(), conLblSecondNumber = new Array(), conTxtSecondNumber = new Array()
                createNumberInputElementTogetherWithItsLabelElementAndSetTheirPrpertiesOfInterest(conLblFirstNumber, conTxtFirstNumber, 
                conIntUnitlessWidthOfTextBox)
                createNumberInputElementTogetherWithItsLabelElementAndSetTheirPrpertiesOfInterest(conLblSecondNumber, conTxtSecondNumber, 
                conIntUnitlessWidthOfTextBox)
                createElement("br")
                const conIntUnitlessWidthOfTheGapBetweenALabelAndItsCorrespondingTextBox = 3, conIntUnitlessWidthOfTheGapBetweenTextBoxes = 
                conLblSecondNumber[0].getBoundingClientRect().width + 20
                conTxtFirstNumber[0].style.left = (screen.availWidth - conIntUnitlessWidthOfTheGapBetweenTextBoxes - 2 * conIntUnitlessWidthOfTextBox) / 
                2 + "px"
                conTxtSecondNumber[0].style.left = conTxtFirstNumber[0].getBoundingClientRect().right + conIntUnitlessWidthOfTheGapBetweenTextBoxes + 
                "px"
                conLblFirstNumber[0].style.left = conTxtFirstNumber[0].getBoundingClientRect().left - conLblFirstNumber[0].getBoundingClientRect().width - 
                conIntUnitlessWidthOfTheGapBetweenALabelAndItsCorrespondingTextBox + "px"
                conLblSecondNumber[0].style.left = conTxtSecondNumber[0].getBoundingClientRect().left - conLblSecondNumber[0].getBoundingClientRect().
                width - conIntUnitlessWidthOfTheGapBetweenALabelAndItsCorrespondingTextBox + "px"
                const conBtnOk = createElement("button")
                conBtnOk.innerHTML = "OK"
                conBtnOk.setAttribute("type", "button")
                conBtnOk.style.display = "block"
                conBtnOk.style.margin = "5px auto"
                conBtnOk.addEventListener("click", function () {
                    const conDblFirstNumber = parseFloat(conTxtFirstNumber[0].value) 
                    const conDblSecondNumber = parseFloat(conTxtSecondNumber[0].value) 
                    let outSum
                    if (outSum == undefined) outSum = createElement("output")
                    outSum.innerHTML = "Sum = " + (conDblFirstNumber + conDblSecondNumber)   
                })          
            }
        </script>
    </head>
    <body id = "body" onload = "computeSum()"></body>
</html>