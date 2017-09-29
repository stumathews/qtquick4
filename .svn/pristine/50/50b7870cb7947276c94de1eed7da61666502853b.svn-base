import QtQuick 2.0 /*Pull in built int QML types like Rectangle, Image...*/


Rectangle // top level item
{
    id: page
    width: 320; height: 480
    color: "lightgray"

    // Lets put some text down on it
    Text
    {
        id: helloText
        text: "Hello World!"
        /* this is where we're gonna put it */
        y: 30
        anchors.horizontalCenter: page.horizontalCenter
        font.pointSize: 24; font.bold: true

        // Lets give this item a mouse area to fill the text button surface
        MouseArea {
            id: mouseArea; anchors.fill: parent
        }

        // Define a custom state for the Text
        states: State {
            name: "down"; when: mouseArea.pressed == true // when is the state triggered!
            // Indicate what should occur(what propety changes occur when this state is met:)
            PropertyChanges { target: helloText; y:160; rotation:180; color: "red" }
            PropertyChanges { target: helloText; text: "Lets go swinging!" }
        }

        // Define transitions for states:
        transitions: Transition {
            from: "" // from which state? "" indicates the default state
            to:"down" // to which state?
            reversible: true // make the opposite state for me!
            ParallelAnimation {
                NumberAnimation { properties: "y, rotation"; duration:500; easing.type: Easing.InOutQuad }
                ColorAnimation { duration: 500 }
            }
        }
    } // Text

    // Put a grid down
    Grid
    {
        id: colorPicker
        x: 4; anchors.bottom: page.bottom; anchors.bottomMargin: 4
        rows: 2; columns: 3; spacing: 3

        // use our custom Cell Component
        Cell { cellColor: "red"; onClicked: helloText.color = cellColor }
        Cell { cellColor: "green"; onClicked: helloText.color = cellColor }
        Cell { cellColor: "blue"; onClicked: helloText.color = cellColor }
        Cell { cellColor: "yellow"; onClicked: helloText.color = cellColor }
        Cell { cellColor: "steelblue"; onClicked: helloText.color = cellColor }
        Cell { cellColor: "black"; onClicked: helloText.color = cellColor }
    }
}
