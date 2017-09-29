import QtQuick 2.0

// Lets make out own custom component!
Item // all components are of type "Item"
{
    id: container
    // Lets set an external visible property:
    property alias cellColor: rectangle.color
    // We call this function when we want emit a clicked signal. Its basically a public viewable function
    signal clicked(color cellColor)
    width: 40; height: 25

    Rectangle
    {
        id: rectangle
        border.color: "white"
        anchors.fill: parent
    }

    MouseArea
    {
        anchors.fill: parent
        /* When the mouse are is clicked, call the signal with parameter and anyone who binds to it will
          get the parameter and do something with it on the outside.
          */
        onClicked: container.clicked(container.cellColor)
    }
}
