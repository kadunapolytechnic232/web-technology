<!DOCTYPE html>
<html>
    <head>
        <title>Examination Result Sheet</title>
        <script>
            function createElement(conStrParentId, conStrElementTypeName, conIntElementTypeCount) {
                const conEltCreatedElement = document.createElement(conStrElementTypeName)
                document.getElementById(conStrParentId).appendChild(conEltCreatedElement)
                let strElementId = conStrElementTypeName
                if (conIntElementTypeCount != undefined) strElementId += conIntElementTypeCount
                if (conStrElementTypeName.startsWith("td") || conStrElementTypeName.startsWith("th")) {
                    conEltCreatedElement.style.border = "groove 3px"
                }
                conEltCreatedElement.setAttribute("id", strElementId)
                return conEltCreatedElement
            }

            function createExamResultTable() {
                const conTblTable = createElement("body", "table")
                const conStrData = [
                    ["th", "S/N", "REGNO", "NAME", "C/WORK", "EXAM", "TOTAL"], 
                    ["th", "[40%]", "[100%]", "[60%]", "[40% + 60%]"], 
                    ["td", "17/2314", "ISAH SALEH", "38", "77", "46"], 
                    ["td", "17/5287", "EMMANUEL DAVID", "30", "68", "41"], 
                    ["td", "17/3488", "SAMUEL JOHN" , "25", "56", "34"]
                ];
                
                for (let intI = 0; intI < conStrData.length; intI++) {
                    createElement("table", "tr", intI)
                    const conRowRowId = "tr" + intI, conIntLargestIndex = conStrData[intI].length - 1, conCellCell = new Array()
                    for (let intJ = 0; intJ < conIntLargestIndex; intJ++) {
                        if (intI > 1) {
                            if (intJ == 0) {
                                createCellElementAndSetItsContent(conCellCell, conRowRowId, conStrData[intI][0], intI - 1)
                            } else if (intJ > 2) {
                                conCellCell[0].style.textAlign = "center"
                            }
                        }
                        createCellElementAndSetItsContent(conCellCell, conRowRowId, conStrData[intI][0], conStrData[intI][intJ + 1], intJ)
                        if (intI + 1 == 1) {
                            if (conCellCell[0].innerHTML == "EXAM") {
                                conCellCell[0].colSpan = "2"
                            } else if (conCellCell[0].innerHTML == "C/WORK" || conCellCell[0].innerHTML == "TOTAL") {
                                conCellCell[0].colSpan = "1"
                            } else {                            
                                conCellCell[0].rowSpan = "2"                            
                            }
                        }
                    }  
                    if (intI > 1) {
                        createCellElementAndSetItsContent(conCellCell, conRowRowId, conStrData[intI][0], parseFloat(conStrData[intI][
                        conIntLargestIndex - 2]) + parseFloat(conStrData[intI][conIntLargestIndex]), conIntLargestIndex)
                        conCellCell[0].style.textAlign = "center"
                    }                    
                }
                conTblTable.style.border = "groove 5px"
                conTblTable.style.borderCollapse = "collapse"
            }

            function createCellElementAndSetItsContent(conCellCell, conRowRowId, conStrCellTypeName, conStrInnerHTML, conIntCellTypeCount) {
                conCellCell[0] = createElement(conRowRowId, conStrCellTypeName, conIntCellTypeCount)
                conCellCell[0].innerHTML = conStrInnerHTML
            }
        </script>
    </head>
    <body id = "body" onload = "createExamResultTable()"></body>
</html>