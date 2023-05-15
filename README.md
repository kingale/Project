var elementNumber = getColumn("Periodic Table Elements", "Period Number");
var elementAtomicWeight = getColumn("Periodic Table Elements", "Atomic Weight");
var elementName = getColumn("Periodic Table Elements", "Name");
var elementSymbol = getColumn("Periodic Table Elements", "Symbol");
var elementGroup = getColumn("Periodic Table Elements", "Atom Classification");
var userChoice;
//main variables
var filteredElementNumber=[];
var filteredAtomicWeight=[];
var filteredElementName=[];
var filteredElementSymbol=[];
var filteredElementGroup=[];
//filtered variables
function filter() {
//filters the info
filteredElementNumber=[];
filteredAtomicWeight=[];
filteredElementName=[];
filteredElementSymbol=[];
filteredElementGroup=[];
for (var i = 0; i < elementName.length; i++) {
  if (elementGroup[i] == userChoice) {
    appendItem(filteredElementNumber, elementNumber[i]);
    appendItem(filteredAtomicWeight, elementAtomicWeight[i]);
    appendItem(filteredElementName, elementName[i]);
    appendItem(filteredElementSymbol, elementSymbol[i]);
    appendItem(filteredElementGroup, elementGroup[i]);
  }
}
}
function outputList() {
//this is the output list that displays the output information
var randomIndex = randomNumber(0, filteredElementNumber.length - 1);
setText("numberM", filteredElementNumber[randomIndex]);
setText("groupM", filteredElementGroup[randomIndex]);
setText("weightM", filteredAtomicWeight[randomIndex]);
setText("nameM", filteredElementName[randomIndex]);
}
onEvent("mainDrop", "change", function( ) {
  userChoice = getText("mainDrop");
  setScreen("Second");
  filter();
  outputList();
});
//function for the output list
onEvent("homeM", "click", function( ) {
  setScreen("Main");
});
onEvent("homeN", "click", function( ) {
  setScreen("Main");
});
onEvent("homeS", "click", function( ) {
  setScreen("Main");
});
//Homescreen buttons to go back to the main screen 
