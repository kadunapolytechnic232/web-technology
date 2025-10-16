<!DOCTYPE html>
<html>
    <head>
        <script>
            function createElement(conStrElementTypeName, conStrParentId = document.getElementById("form")) {
                return conStrParentId.appendChild(document.createElement(conStrElementTypeName))
            }

            function computetrGrade() {
                const conFrmForm = createElement("form", document.getElementById("body"))
                conFrmForm.setAttribute("id", "form")
                const conTxtScoresCount = createElement("input")
                const conBtnOk = createElement("button")
                conBtnOk.innerHTML = "OK"
                conBtnOk.setAttribute("type", "button")
                conBtnOk.addEventListener("click", function () {
                    if (conBtnOk.blnTheOkButtonHasOnceBeenClicked) {
                        conBtnOk.blnTheOkButtonHasOnceBeenClicked = false
                        const conScore = document.getElementsByClassName("score")                        
                        let strGrade = ""
                        const conStrGrade = new Array()
                        for (let intI = 0; intI < conScore.length; intI++) {
                            const conIntScore = parseInt(conScore[intI].value) 
                            switch (true) {
                                case (conIntScore < 0 || conIntScore > 100): 
                                    conStrGrade[intI] = "Invalid score (and/or grade)!"
                                case (conIntScore < 40):  
                                    conStrGrade[intI] = "F"
                                    break
                                case (conIntScore >= 40 && conIntScore <= 44): 
                                    conStrGrade[intI] = "E"     
                                    break                 
                                case (conIntScore >= 45 && conIntScore <= 49):
                                    conStrGrade[intI] = "D"   
                                    break
                                case (conIntScore >= 50 && conIntScore <= 59):
                                    conStrGrade[intI] = "C"   
                                    break
                                case (conIntScore >= 60 && conIntScore <= 69):
                                    conStrGrade[intI] = "B"    
                                    break         
                                default:
                                    conStrGrade[intI] = "A"
                            }
                            strGrade += conStrGrade[intI] + ", "
                        }
                        if (conBtnOk.outGrade == undefined) conBtnOk.outGrade = createElement("output")
                        conBtnOk.outGrade.innerHTML = "Grade: " + strGrade.substring(0, strGrade.length - 2)
                    } else {
                        conBtnOk.blnTheOkButtonHasOnceBeenClicked = true
                        for (let intI = 0; intI < parseInt(conTxtScoresCount.value); intI++) {
                            const conTxtScore = createElement("input") 
                            conTxtScore.setAttribute("class", "score")
                        }
                    }                  
                })          
            }
        </script>
    </head>
    <body id = "body" onload = "computetrGrade()"></body>
</html>