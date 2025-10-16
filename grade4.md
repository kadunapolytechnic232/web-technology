<!DOCTYPE html>
<html>
    <head>
        <script>
            let intWidthOfTheGapBetweenTextBoxes, intCurrentScoresCount
            const conIntUnitlessGapBetweenContigousElements = 3, conStrGapBetweenContigousElements = conIntUnitlessGapBetweenContigousElements + "px"
            
            function conEltDynamicallyCreatedElementAppendedToItsParent(conStrElementTypeName, conStrParentId = document.getElementById("form")) {
                return conStrParentId.appendChild(document.createElement(conStrElementTypeName))
            }

            function computeGrade() {
                const conIntUnitLessWidthOfScreen = screen.availWidth, conIntUnitLessWidthOfATextBox = 38
                let intHalfOfTheWidthOfTheGapBetweenTextBoxes
                const conFrmForm = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.position:absolute", 
                "style.boxSizing:border-box", "style.left:0", `style.width:${conIntUnitLessWidthOfScreen}px`], "form", document.getElementById("body"))
                const conDivDiv = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.boxSizing:border-box", `style.width:${
                conIntUnitLessWidthOfScreen}px`], "div")
                const conTxtScoresCount = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.position:absolute", 
                "style.boxSizing:border-box", `style.width:${conIntUnitLessWidthOfATextBox}px`, `style.left:${(conIntUnitLessWidthOfScreen - 
                conIntUnitLessWidthOfATextBox) / 2}px`], "input", conDivDiv)
                const conLblScoresCount = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.position:absolute", 
                "style.boxSizing:border-box", "style.textWrap:nowrap", "style.width:auto", "innerHTML:Scores Count", `style.left:${conTxtScoresCount.
                getBoundingClientRect().left - conIntUnitlessGapBetweenContigousElements}`], "label", conDivDiv)
                const conIntUnitlessTopOfDiv = conDivDiv.getBoundingClientRect().top
                const conBtnOk = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.boxSizing:border-box", "innerHTML:Ok",
                "style.position:absolute", "type:button", `style.left:${conIntUnitLessWidthOfScreen / 2}`, `style.top:${conTxtScoresCount.
                getBoundingClientRect().bottom - conIntUnitlessTopOfDiv + conIntUnitlessGapBetweenContigousElements}px`], "button", conDivDiv)
                conDivDiv.style.height = conBtnOk.getBoundingClientRect().bottom - conIntUnitlessTopOfDiv + conIntUnitlessGapBetweenContigousElements + 
                "px"
                conBtnOk.addEventListener("click", function () {        
                    if (conBtnOk.addEventListener.blnTheClickEventHasOnceBeenTriggeredOnTheOkButton) {
                        conBtnOk.addEventListener.blnTheClickEventHasOnceBeenTriggeredOnTheOkButton = false
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
                        if (conBtnOk.outGrade == undefined) {
                            conBtnOk.outGrade = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.position:absolute", 
                            "style.boxSizing:border-box", "style.textWrap:nowrap", "style.width:auto", `innerHTML:Grade: ${strGrade.substring(0, 
                            strGrade.length - 2)}`, `style.left:${conBtnOk.intUnitLessWidthOfFormAndDiv / 2 + intHalfOfTheWidthOfTheGapBetweenTextBoxes}`,
                            `style.top:${conBtnOk.getBoundingClientRect().bottom - conIntUnitlessTopOfDiv}px`], "output")
                        }
                        conFrmForm.style.height = conBtnOk.outGrade.getBoundingClientRect().bottom + "px"
                    } else {
                        conBtnOk.addEventListener.blnTheClickEventHasOnceBeenTriggeredOnTheOkButton = true
                        conDivDiv.style.height = conBtnOk.style.top
                        intCurrentScoresCount = parseFloat(conTxtScoresCount.value)
                        const conLblWidestArraySymbolLabelElementContainingSubElementForSubscript = 
                        conLblArraySymbolLabelElementContainingSubElementForSubscript("2".repeat(intCurrentScoresCount.toString().length))
                        conFrmForm.removeChild(conLblWidestArraySymbolLabelElementContainingSubElementForSubscript)                        
                        const conLblScoreTextInputElementSubscriptedVariableLabel = new Array(), conTxtScoreTextInputElement = new Array(),
                        conIntWidthOfTheArrayOfAllOfTheScoreTextInputElementsTogetherWithTheGapsBetweenThem = (intCurrentScoresCount * 
                        (intWidthOfTheGapBetweenTextBoxes + conIntUnitLessWidthOfATextBox))
                        conFrmForm.style.width = conIntUnitLessWidthOfScreen - intWidthOfTheGapBetweenTextBoxes + "px"
                        let intI = 0
                        do {
                            intI += 1
                            createScoreTextInputElementTogetherWithItsSubscriptedVariableLabelElement(
                            conLblScoreTextInputElementSubscriptedVariableLabel, conTxtScoreTextInputElement, conIntUnitLessWidthOfATextBox, 
                            intI)
                        } while (intI < intCurrentScoresCount && conTxtScoreTextInputElement[0].getBoundingClientRect().top == conFrmForm.
                        children[2].getBoundingClientRect().top)
                        let intIndexOfRightmostTextInputElement = conFrmForm.children.length - 1, intJ = intI
                        if (intI < intCurrentScoresCount) {
                            if (conTxtScoreTextInputElement[0].getBoundingClientRect().top == conFrmForm.children[2].getBoundingClientRect().top) {
                                intJ += 1
                            } else {
                                intIndexOfRightmostTextInputElement -= 2
                            }
                        }
                        conBtnOk.intUnitLessWidthOfFormAndDiv = conFrmForm.children[intIndexOfRightmostTextInputElement].getBoundingClientRect().right
                        const conStrWidthOfFormAndDiv = conBtnOk.intUnitLessWidthOfFormAndDiv + "px"
                        setTheValueOfPropertyOfFormAndItsFirstChild_whichIsTheLoneDivElement(conFrmForm, "width", conStrWidthOfFormAndDiv)
                        for (let intI = intJ; intI < intCurrentScoresCount; intI++) {
                            createScoreTextInputElementTogetherWithItsSubscriptedVariableLabelElement(
                            conLblScoreTextInputElementSubscriptedVariableLabel, conTxtScoreTextInputElement, conIntUnitLessWidthOfATextBox, intI + 1)
                            conTxtScoreTextInputElement[0].style.marginTop = conStrGapBetweenContigousElements
                        }
                        intHalfOfTheWidthOfTheGapBetweenTextBoxes = intWidthOfTheGapBetweenTextBoxes / 2                        
                        const conStrLeftOfFormAndDiv = (conIntUnitLessWidthOfScreen - conBtnOk.intUnitLessWidthOfFormAndDiv - 
                        intWidthOfTheGapBetweenTextBoxes) / 2 + "px"  
                        setTheValueOfPropertyOfFormAndItsFirstChild_whichIsTheLoneDivElement(conFrmForm, "left", conStrLeftOfFormAndDiv)
                        const conIntUnitlessLeftOfScoresCountTextInputElement = (conBtnOk.intUnitLessWidthOfFormAndDiv - conIntUnitLessWidthOfATextBox
                        ) / 2 + intHalfOfTheWidthOfTheGapBetweenTextBoxes
                        conTxtScoresCount.style.left = conIntUnitlessLeftOfScoresCountTextInputElement + "px"
                        conLblScoresCount.style.left = conIntUnitlessLeftOfScoresCountTextInputElement - conLblScoresCount.getBoundingClientRect().
                        width - conIntUnitlessGapBetweenContigousElements + "px"
                        const conIntUnitlessBottomOfTheLastFormChildAndOrScoreTextInputElement = conFrmForm.children[conFrmForm.children.length - 1].
                        getBoundingClientRect().bottom
                        conBtnOk.style.left = (conBtnOk.intUnitLessWidthOfFormAndDiv - conBtnOk.getBoundingClientRect().width) / 2 + 
                        intHalfOfTheWidthOfTheGapBetweenTextBoxes + "px"
                        conBtnOk.style.top = conIntUnitlessBottomOfTheLastFormChildAndOrScoreTextInputElement - conIntUnitlessTopOfDiv + 
                        conIntUnitlessGapBetweenContigousElements + "px"
                        conFrmForm.style.height = conIntUnitlessBottomOfTheLastFormChildAndOrScoreTextInputElement + "px"  
                    }                  
                })          
            }

            function setTheValueOfPropertyOfFormAndItsFirstChild_whichIsTheLoneDivElement(conFrmForm, conStrProperty, conStrPropertyValue) {                
                conFrmForm.style[conStrProperty] = conStrPropertyValue
                conFrmForm.children[0].style[conStrProperty] = conStrPropertyValue
            }
            
            function conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(conStrStringOfCommaSeparatedPropertyAndValuePair, 
            conStrElementTypeName, conStrParentId) {
                let eltElement
                if (conStrElementTypeName == "output") {
                    const conOutGrade = document.getElementById("output")
                    if (conOutGrade == undefined) eltElement = conEltDynamicallyCreatedElementAppendedToItsParent(conStrElementTypeName, conStrParentId)
                } else {
                    eltElement = conEltDynamicallyCreatedElementAppendedToItsParent(conStrElementTypeName, conStrParentId)
                }
                let intLength = conStrStringOfCommaSeparatedPropertyAndValuePair.length
                for (let intI = 0; intI < intLength; intI++) {
                    createElementAndSetTheValuesOfItsPropertiesOfInterest(eltElement, conStrStringOfCommaSeparatedPropertyAndValuePair, intI)
                }
                if (!(conStrStringOfCommaSeparatedPropertyAndValuePair[intLength - 2] == "class:score" && 
                conStrStringOfCommaSeparatedPropertyAndValuePair[intLength - 1].startsWith("id:score"))) {
                    conStrStringOfCommaSeparatedPropertyAndValuePair.push("id:" + conStrElementTypeName)
                } else {
                    intLength -= 1
                }
                createElementAndSetTheValuesOfItsPropertiesOfInterest(eltElement, conStrStringOfCommaSeparatedPropertyAndValuePair, intLength)
                return eltElement
            }

            function createElementAndSetTheValuesOfItsPropertiesOfInterest(conEltElement, conStrStringOfCommaSeparatedPropertyAndValuePair, intI) {
                const conIntPositionOfColon = conStrStringOfCommaSeparatedPropertyAndValuePair[intI].indexOf(":"), conStrProperty = 
                conStrStringOfCommaSeparatedPropertyAndValuePair[intI].substring(0, conIntPositionOfColon), conStrPropertyValue = 
                conStrStringOfCommaSeparatedPropertyAndValuePair[intI].substring(conIntPositionOfColon + 1)       
                if (conStrProperty.startsWith("style")) {                    
                    const conStrPropertyOfTheStyleProperty = conStrProperty.substring(conStrProperty.indexOf(".") + 1)
                    if (conStrPropertyOfTheStyleProperty == "left") {
                        if (isFinite(conStrPropertyValue)) {
                            const conDblWidth = conEltElement.getBoundingClientRect().width
                            let intUnitlessLeft = conStrPropertyValue
                            if (conEltElement.innerHTML == "Scores Count") {
                                intUnitlessLeft -= conDblWidth
                            } else {
                                intUnitlessLeft -= conDblWidth / 2
                            }
                            conEltElement.style[conStrPropertyOfTheStyleProperty] = intUnitlessLeft + "px"
                        } else {
                            conEltElement.style[conStrPropertyOfTheStyleProperty] = conStrPropertyValue
                        }
                    } else {
                        if (conStrPropertyOfTheStyleProperty == "marginLeft") {
                            const conDblWidth = conEltElement.getBoundingClientRect().width
                            if (conStrPropertyValue == "undefinedpx") intWidthOfTheGapBetweenTextBoxes = conDblWidth + 15 
                            conEltElement.style[conStrPropertyOfTheStyleProperty] = intWidthOfTheGapBetweenTextBoxes - conDblWidth + "px"
                        } else {
                            conEltElement.style[conStrPropertyOfTheStyleProperty] = conStrPropertyValue
                        }
                    }
                } else {
                    if (conStrProperty == "class") {
                        conEltElement.setAttribute(conStrProperty, conStrPropertyValue)
                    } else {
                        conEltElement[conStrProperty] = conStrPropertyValue
                    }
                }
            }

            function conLblArraySymbolLabelElementContainingSubElementForSubscript(conIntSubscript) {
                let strSubscript = conIntSubscript
                if (conIntSubscript == 1 && intCurrentScoresCount == 1) strSubscript = ""
                const conStrProperty = ["style.boxSizing:border-box", "style.textWrap:nowrap", "style.width:auto", `innerHTML:${"X"}<sub style = 
                "font-size:11px; margin-right:${conStrGapBetweenContigousElements}">${strSubscript}</sub>`, `style.marginLeft:${
                intWidthOfTheGapBetweenTextBoxes}px`]
                if (conLblArraySymbolLabelElementContainingSubElementForSubscript.
                blnTheWidthOfTheGapBetweenTextBoxesDeterminantSubscriptedVariableLabelHasBeenCreated) {
                    conStrProperty.push(`for:score${strSubscript}`)
                } else {
                    conLblArraySymbolLabelElementContainingSubElementForSubscript.
                    blnTheWidthOfTheGapBetweenTextBoxesDeterminantSubscriptedVariableLabelHasBeenCreated = true
                }
                return conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(conStrProperty, "label")
            }

            function createScoreTextInputElementTogetherWithItsSubscriptedVariableLabelElement(lblScoreTextInputElementSubscriptedVariableLabel, 
            txtScoreTextInputElement, conIntUnitLessWidthOfATextBox, conIntI) {
                lblScoreTextInputElementSubscriptedVariableLabel[0] = conLblArraySymbolLabelElementContainingSubElementForSubscript(conIntI)
                const conTxtScore = conEltCreatedElementWithValuesOfItsPropertiesOfInterestBeingSet(["style.boxSizing:border-box", 
                `style.width:${conIntUnitLessWidthOfATextBox}px`, "class:score", `id:score${conIntI}`], "input")
                txtScoreTextInputElement[0] = conTxtScore
            }
        </script>
    </head>
    <body id = "body" onload = "computeGrade()"></body>
</html>