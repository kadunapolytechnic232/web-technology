<!DOCTYPE html>
<html>
    <head>
        <script>
            function createElement(conStrElementTypeName, conStrParentId = document.getElementById("form")) {
                return conStrParentId.appendChild(document.createElement(conStrElementTypeName))
            }

            function computeSum() {
                const conFrmForm = createElement("form", document.getElementById("body"))
                conFrmForm.setAttribute("id", "form")
                const conTxtNumbersCount = createElement("input")
                const conBtnOk = createElement("button")
                conBtnOk.innerHTML = "OK"
                conBtnOk.setAttribute("type", "button")
                conBtnOk.addEventListener("click", function () {
                    if (conBtnOk.blnTheOkButtonHasOnceBeenClicked) {
                        conBtnOk.blnTheOkButtonHasOnceBeenClicked = false
                        const conNumber = document.getElementsByClassName("number")
                        let dblSum = 0
                        for (let intI = 0; intI < conNumber.length; intI++) dblSum += parseFloat(conNumber[intI].value)                 
                        if (conBtnOk.outSum == undefined) conBtnOk.outSum = createElement("output")
                        conBtnOk.outSum.innerHTML = "Sum = " + dblSum
                    } else {
                        conBtnOk.blnTheOkButtonHasOnceBeenClicked = true
                        for (let intI = 0; intI < parseInt(conTxtNumbersCount.value); intI++) {
                            const conTxtNumber = createElement("input") 
                            conTxtNumber.setAttribute("class", "number")
                        }
                    }                  
                })          
            }
        </script>
    </head>
    <body id = "body" onload = "computeSum()"></body>
</html>