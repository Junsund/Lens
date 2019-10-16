sel = activeDocument.selection;
selObj = activeDocument.pathItems;

for (var i=0; i<selObj.length; i++)
{
    selObj[i].selected = true;
    var p1x = selObj[i].pathPoints[0].anchor[0];
    var p1y = selObj[i].pathPoints[0].anchor[1];
    var p2x = selObj[i].pathPoints[1].anchor[0];
    var p2y = selObj[i].pathPoints[1].anchor[1];
}

gObj = activeDocument.groupItems.add();
for (var i=0; i<sel.length; i++)
    {
    sel[i].move(gObj,ElementPlacement.PLACEATEND);
    }

if (p1x == p1y){}
else
{
    var d = Math.atan2(Math.abs(p1y-p2y),p2x-p1x);
    gsel = activeDocument.groupItems;
    for (i=0; i<gsel.length; i++){
        gsel[i].rotate((d* ( 180 / Math.PI ))-90,true,false,false,false,Transformation.CENTER);
    }
}
