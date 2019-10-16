//レンズ構成図を書くだけのスクリプト

var linesize=0.5;

var lineColorR = new RGBColor();
lineColorR.red   = 255;
lineColorR.green = 0;
lineColorR.blue  = 0;
var lineColorG = new RGBColor();
lineColorG.red   = 0;
lineColorG.green = 255;
lineColorG.blue  = 0;
var lineColorB = new RGBColor();
lineColorB.red   = 25;
lineColorB.green = 25;
lineColorB.blue  = 25;
var lineColorGr = new RGBColor();
lineColorGr.red   = 128;
lineColorGr.green = 128;
lineColorGr.blue  = 128;
var lineColorN = new RGBColor();
lineColorN.red   = 255;
lineColorN.green = 128;
lineColorN.blue  = 0;
var lineColorBl = new RGBColor();
lineColorBl.red   = 0;
lineColorBl.green = 0;
lineColorBl.blue  = 0;
var lineColorP = new RGBColor();
lineColorP.red   = 200;
lineColorP.green = 0;
lineColorP.blue  = 200;


function bubblesort()
{
    sel= app.activeDocument.selection; 
    for(var i = 0; i < sel.length-1; i++){
        //後ろから前に向かって小さい値を浮かび上がらせるfor文
        for(var j =0;j<sel.length-i-1;  j++){
            //隣りあう２つの値を比べて、後ろが小さければ交換する
            if(Math.abs(sel[j].pathPoints[1].anchor[1])>Math.abs(sel[j+1].pathPoints[1].anchor[1])){
                var tmp = sel[j];
                sel[j] = sel[j+1];
                sel[j+1] =tmp;
            }
        }
    }
}

function selchangecolorR()
{
    app.executeMenuCommand("deselectall");
    dummyC = activeDocument.pathItems.add();
    dummyC .setEntirePath([[0,0],[0,0]]);
    dummyC .filled = false; // 塗りなし
    dummyC .stroked = true; // 線あり
    dummyC .strokeColor= lineColorR; //色指定
    dummyC .strokeWidth = linesize;
    dummyC .selected = true; //選択する
    app.executeMenuCommand("Find Stroke Color menu item");
    dummyC .remove();
}

function selchangecolorG()
{
    app.executeMenuCommand("deselectall");
    dummyC = activeDocument.pathItems.add();
    dummyC .setEntirePath([[0,0],[0,0]]);
    dummyC .filled = false; // 塗りなし
    dummyC .stroked = true; // 線あり
    dummyC .strokeColor= lineColorG; //色指定
    dummyC .strokeWidth = linesize;
    dummyC .selected = true;
    app.executeMenuCommand("Find Stroke Color menu item");
    dummyC .remove();
}

function selchangecolorB()
{
    app.executeMenuCommand("deselectall");
    dummyC = activeDocument.pathItems.add();
    dummyC .setEntirePath([[0,0],[0,0]]);
    dummyC .filled = false; // 塗りなし
    dummyC .stroked = true; // 線あり
    dummyC .strokeColor= lineColorB; //色指定
    dummyC .strokeWidth = linesize;
    dummyC .selected = true; //選択する
    app.executeMenuCommand("Find Stroke Color menu item");
    dummyC .remove();
}

function selchangecolorGr()
{
    app.executeMenuCommand("deselectall");
    dummyC = activeDocument.pathItems.add();
    dummyC .setEntirePath([[0,0],[0,0]]);
    dummyC .filled = false; // 塗りなし
    dummyC .stroked = true; // 線あり
    dummyC .strokeColor= lineColorGr; //色指定
    dummyC .strokeWidth = linesize;
    dummyC .selected = true; //選択する
    app.executeMenuCommand("Find Stroke Color menu item");
    dummyC .remove();
}

function selchangecolorN()
{
    app.executeMenuCommand("deselectall");
    dummyC = activeDocument.pathItems.add();
    dummyC .setEntirePath([[0,0],[0,0]]);
    dummyC .filled = false; // 塗りなし
    dummyC .stroked = true; // 線あり
    dummyC .strokeColor= lineColorN; //色指定
    dummyC .strokeWidth = linesize;
    dummyC .selected = true; //選択する
    app.executeMenuCommand("Find Stroke Color menu item");
    dummyC .remove();
}

function selchangecolorP()
{
    app.executeMenuCommand("deselectall");
    dummyC = activeDocument.pathItems.add();
    dummyC .setEntirePath([[0,0],[0,0]]);
    dummyC .filled = false; // 塗りなし
    dummyC .stroked = true; // 線あり
    dummyC .strokeColor= lineColorP; //色指定
    dummyC .strokeWidth = linesize;
    dummyC .selected = true; //選択する
    app.executeMenuCommand("Find Stroke Color menu item");
    dummyC .remove();
}

//一番上を選択。絶対レンズだから
app.executeMenuCommand("selectall");
sel= app.activeDocument.selection;
var p2ytop=-50000000;
for(var i = 0; i<sel.length; i++){
    var p1x = sel[i].pathPoints[0].anchor[0];
    var p1y = sel[i].pathPoints[0].anchor[1];
    var p2x = sel[i].pathPoints[1].anchor[0];
    var p2y = sel[i].pathPoints[1].anchor[1];
    if(p2ytop<p2y){
        p2ytop = p2y
    }
}
app.executeMenuCommand("selectall");
sel= app.activeDocument.selection;
for(var i = 0; i<sel.length; i++){
    var p1x = sel[i].pathPoints[0].anchor[0];
    var p1y = sel[i].pathPoints[0].anchor[1];
    var p2x = sel[i].pathPoints[1].anchor[0];
    var p2y = sel[i].pathPoints[1].anchor[1];
    if(p2ytop==p2y){
        app.executeMenuCommand("deselectall");
        sel[i].selected = true;
    }
}

// 黒線(レンズ指標線)を左から右へ書いた様に再描写する。
app.executeMenuCommand("Find Stroke Color menu item");
bubblesort();
for(var i = 0; i<sel.length; i++){
    var p1x = sel[i].pathPoints[0].anchor[0];
    var p1y = sel[i].pathPoints[0].anchor[1];
    var p2x = sel[i].pathPoints[1].anchor[0];
    var p2y = sel[i].pathPoints[1].anchor[1];
    // 最初に書いた線が左か右かで今後結果が変わってくるので、いっそのこと←に再描写してしまう。
    //これによって左側がp1に統一
    if(p1x>p2x){
        lObj = activeDocument.pathItems.add();
        lObj.setEntirePath([[p2x,p2y],[p1x,p1y]]);
        lObj.filled = false; // 塗りなし
        lObj.stroked = true; // 線あり
        lObj.strokeColor= lineColorB; //色指定
        lObj.strokeWidth = linesize;
        lObj.selected = true; //選択する
        sel[i].remove(); //元を消す
    }
    else{
        // 最初から右向き→であった場合も書き直す。
        lObj = activeDocument.pathItems.add();
        lObj.setEntirePath([[p1x,p1y],[p2x,p2y]]);
        lObj.filled = false; // 塗りなし
        lObj.stroked = true; // 線あり
        lObj.strokeColor= lineColorB; //色指定
        lObj.strokeWidth = linesize;
        lObj.selected = true; //選択する
        sel[i].remove();
    }
}

//レンズの被写体面をlensTop、フィルム側をlensRearとする。
selchangecolorB()
bubblesort();
for(var i = 0; i<sel.length; i++){
    var p1x = sel[i].pathPoints[0].anchor[0];
    var p1y = sel[i].pathPoints[0].anchor[1];
    var p2x = sel[i].pathPoints[1].anchor[0];
    var p2y = sel[i].pathPoints[1].anchor[1];
    if (i % 2 ==0){ 
        sel[i].name = "lensTop";
    }
    else{  
        sel[i].name = "lensRear";
    }
}

//レンズの側面指標線を処理
app.executeMenuCommand("Inverse menu item");//無選択だったモノを選択から右へ書いた様に再描写する。
bubblesort();
for(var i = 0; i<sel.length; i++){
    var p1x = sel[i].pathPoints[0].anchor[0];
    var p1y = sel[i].pathPoints[0].anchor[1];
    var p2x = sel[i].pathPoints[1].anchor[0];
    var p2y = sel[i].pathPoints[1].anchor[1];
    //これも最初に書いた線が左か右かで今後結果が変わってくるので、いっそのこと←に再描写してしまう。
    //これによって左側がp1に統一
    if(p1x>p2x){
        lObj = activeDocument.pathItems.add();
        lObj.setEntirePath([[p2x,p2y],[p1x,p1y]]);
        lObj.filled = false; // 塗りなし
        lObj.stroked = true; // 線あり
        lObj.strokeColor= lineColorR; //色指定
        lObj.strokeWidth = linesize;
        lObj.selected = true; //選択する
        lObj.name = "red"; //名前
        sel[i].remove();
    }
    else{
        // 最初から右向き→であった場合も書き直す。
        lObj = activeDocument.pathItems.add();
        lObj.setEntirePath([[p1x,p1y],[p2x,p2y]]);
        lObj.filled = false; // 塗りなし
        lObj.stroked = true; // 線あり
        lObj.strokeColor= lineColorR; //色指定
        lObj.strokeWidth = linesize;
        lObj.selected = true; //選択する
        lObj.name = "red"; //名前
        sel[i].remove();
        
    }
}

//右揃え
app.executeMenuCommand("selectall");
sel= app.activeDocument.selection;
var rEnd =0;
for(var i = 0; i<sel.length; i++){
    var p1r = sel[i].geometricBounds[2];
    if(rEnd<p1r){
        rEnd=p1r;
    }
}

app.executeMenuCommand("selectall");
sel= app.activeDocument.selection;
for(var i = 0; i<sel.length; i++){
    var p1r = sel[i].geometricBounds[2];
    if(rEnd !==p1r){
        sel[i].position=[rEnd-(sel[i].geometricBounds[2]-sel[i].geometricBounds[0]),sel[i].geometricBounds[1]];
    }
}

//レンズ側面の描写。
//下から処理している。
app.executeMenuCommand("selectall");
sel= app.activeDocument.selection;
bubblesort();
for(var i = sel.length-1; i>=0; i--)
    {
    var p1x = sel[i].pathPoints[0].anchor[0]; 
    var p1y = sel[i].pathPoints[0].anchor[1];
    var p2x = sel[i].pathPoints[1].anchor[0];
    var p2y = sel[i].pathPoints[1].anchor[1];
    if(sel[i].name=="lensTop"){
        if(sel[i+1].name=="red"){
            if(sel[i+2].name=="red"){
                if(sel[i+3].name=="red"){
                    if(sel[i+4].name=="red"){
                        if(sel[i+5].name=="red"){
                        }
                        else{
                            //サイド角が四ある場合
                            var p3x = sel[i+1].pathPoints[0].anchor[0]; 
                            var p3y = sel[i+1].pathPoints[0].anchor[1];
                            var p4x = sel[i+1].pathPoints[1].anchor[0];
                            var p4y = sel[i+1].pathPoints[1].anchor[1];
                            var p5x = sel[i+2].pathPoints[0].anchor[0]; 
                            var p5y = sel[i+2].pathPoints[0].anchor[1];
                            var p6x = sel[i+2].pathPoints[1].anchor[0];
                            var p6y = sel[i+2].pathPoints[1].anchor[1];
                            var p7x = sel[i+3].pathPoints[0].anchor[0]; 
                            var p7y = sel[i+3].pathPoints[0].anchor[1];
                            var p8x = sel[i+3].pathPoints[1].anchor[0];
                            var p8y = sel[i+3].pathPoints[1].anchor[1];
                            var p9x = sel[i+4].pathPoints[0].anchor[0]; 
                            var p9y = sel[i+4].pathPoints[0].anchor[1];
                            var p10x = sel[i+4].pathPoints[1].anchor[0];
                            var p10y = sel[i+4].pathPoints[1].anchor[1];
                            var p11x = sel[i+5].pathPoints[0].anchor[0]; 
                            var p11y = sel[i+5].pathPoints[0].anchor[1];
                            var p12x = sel[i+5].pathPoints[1].anchor[0];
                            var p12y = sel[i+5].pathPoints[1].anchor[1];
                            app.executeMenuCommand("deselectall");
                            lObj01 = activeDocument.pathItems.add();
                            lObj01.setEntirePath([[p1x,p1y],[p3x,p3y]]);
                            lObj01.filled = false; // 塗りなし
                            lObj01.stroked = true; // 線あり
                            lObj01.strokeColor= lineColorG; //色指定
                            lObj01.strokeWidth = linesize;
                            lObj01.name = "side"; //名前
                            lObj01.selected = true;
                            lObj03 = activeDocument.pathItems.add();
                            lObj03.setEntirePath([[p3x,p3y],[p5x,p5y]]);
                            lObj03.filled = false; // 塗りなし
                            lObj03.stroked = true; // 線あり
                            lObj03.strokeColor= lineColorG; //色指定
                            lObj03.strokeWidth = linesize;
                            lObj03.name = "side"; //名前
                            lObj03.selected = true;
                            lObj05= activeDocument.pathItems.add();
                            lObj05.setEntirePath([[p5x,p5y],[p7x,p7y]]);
                            lObj05.filled = false; // 塗りなし
                            lObj05.stroked = true; // 線あり
                            lObj05.strokeColor= lineColorG; //色指定
                            lObj05.strokeWidth = linesize;
                            lObj05.name = "side"; //名前
                            lObj05.selected = true;
                            lObj07= activeDocument.pathItems.add();
                            lObj07.setEntirePath([[p7x,p7y],[p9x,p9y]]);
                            lObj07.filled = false; // 塗りなし
                            lObj07.stroked = true; // 線あり
                            lObj07.strokeColor= lineColorG; //色指定
                            lObj07.strokeWidth = linesize;
                            lObj07.name = "side"; //名前
                            lObj07.selected = true;
                            lObj09= activeDocument.pathItems.add();
                            lObj09.setEntirePath([[p11x,p11y],[p9x,p9y]]);
                            lObj09.filled = false; // 塗りなし
                            lObj09.stroked = true; // 線あり
                            lObj09.strokeColor= lineColorG; //色指定
                            lObj09.strokeWidth = linesize;
                            lObj09.name = "side"; //名前
                            lObj09.selected = true;
                            app.executeMenuCommand("join");
                            app.executeMenuCommand("deselectall");
                            lObj02 = activeDocument.pathItems.add();
                            lObj02.setEntirePath([[p1x+(p2x-p1x)*2,p1y],[p3x+(p4x-p3x)*2,p3y]]);
                            lObj02.filled = false; // 塗りなし
                            lObj02.stroked = true; // 線あり
                            lObj02.strokeColor= lineColorP; //色指定
                            lObj02.strokeWidth = linesize;
                            lObj02.name = "side"; //名前
                            lObj02.selected = true;
                            lObj04 = activeDocument.pathItems.add();
                            lObj04.setEntirePath([[p3x+(p4x-p3x)*2,p3y],[p5x+(p6x-p5x)*2,p5y]]);
                            lObj04.filled = false; // 塗りなし
                            lObj04.stroked = true; // 線あり
                            lObj04.strokeColor= lineColorP; //色指定
                            lObj04.strokeWidth = linesize;
                            lObj04.name = "side"; //名前
                            lObj04.selected = true;
                            lObj06 = activeDocument.pathItems.add();
                            lObj06.setEntirePath([[p7x+(p8x-p7x)*2,p7y],[p5x+(p6x-p5x)*2,p5y]]);
                            lObj06.filled = false; // 塗りなし
                            lObj06.stroked = true; // 線あり
                            lObj06.strokeColor= lineColorP; //色指定
                            lObj06.strokeWidth = linesize;
                            lObj06.name = "side"; //名前
                            lObj06.selected = true;
                            lObj08 = activeDocument.pathItems.add();
                            lObj08.setEntirePath([[p9x+(p10x-p9x)*2,p9y],[p7x+(p8x-p7x)*2,p7y]]);
                            lObj08.filled = false; // 塗りなし
                            lObj08.stroked = true; // 線あり
                            lObj08.strokeColor= lineColorP; //色指定
                            lObj08.strokeWidth = linesize;
                            lObj08.name = "side"; //名前
                            lObj08.selected = true;
                            lObj08 = activeDocument.pathItems.add();
                            lObj08.setEntirePath([[p11x+(p12x-p11x)*2,p11y],[p9x+(p10x-p9x)*2,p9y]]);
                            lObj08.filled = false; // 塗りなし
                            lObj08.stroked = true; // 線あり
                            lObj08.strokeColor= lineColorP; //色指定
                            lObj08.strokeWidth = linesize;
                            lObj08.name = "side"; //名前
                            lObj08.selected = true;
                            app.executeMenuCommand("join");
                            app.executeMenuCommand("deselectall");
                        }
                    }
                    else{
                        //サイド角が三ある場合
                        var p3x = sel[i+1].pathPoints[0].anchor[0]; 
                        var p3y = sel[i+1].pathPoints[0].anchor[1];
                        var p4x = sel[i+1].pathPoints[1].anchor[0];
                        var p4y = sel[i+1].pathPoints[1].anchor[1];
                        var p5x = sel[i+2].pathPoints[0].anchor[0]; 
                        var p5y = sel[i+2].pathPoints[0].anchor[1];
                        var p6x = sel[i+2].pathPoints[1].anchor[0];
                        var p6y = sel[i+2].pathPoints[1].anchor[1];
                        var p7x = sel[i+3].pathPoints[0].anchor[0]; 
                        var p7y = sel[i+3].pathPoints[0].anchor[1];
                        var p8x = sel[i+3].pathPoints[1].anchor[0];
                        var p8y = sel[i+3].pathPoints[1].anchor[1];
                        var p9x = sel[i+4].pathPoints[0].anchor[0]; 
                        var p9y = sel[i+4].pathPoints[0].anchor[1];
                        var p10x = sel[i+4].pathPoints[1].anchor[0];
                        var p10y = sel[i+4].pathPoints[1].anchor[1];
                        app.executeMenuCommand("deselectall");
                        lObj01 = activeDocument.pathItems.add();
                        lObj01.setEntirePath([[p1x,p1y],[p3x,p3y]]);
                        lObj01.filled = false; // 塗りなし
                        lObj01.stroked = true; // 線あり
                        lObj01.strokeColor= lineColorG; //色指定
                        lObj01.strokeWidth = linesize;
                        lObj01.name = "side"; //名前
                        lObj01.selected = true;
                        lObj03 = activeDocument.pathItems.add();
                        lObj03.setEntirePath([[p3x,p3y],[p5x,p5y]]);
                        lObj03.filled = false; // 塗りなし
                        lObj03.stroked = true; // 線あり
                        lObj03.strokeColor= lineColorG; //色指定
                        lObj03.strokeWidth = linesize;
                        lObj03.name = "side"; //名前
                        lObj03.selected = true;
                        lObj05= activeDocument.pathItems.add();
                        lObj05.setEntirePath([[p5x,p5y],[p7x,p7y]]);
                        lObj05.filled = false; // 塗りなし
                        lObj05.stroked = true; // 線あり
                        lObj05.strokeColor= lineColorG; //色指定
                        lObj05.strokeWidth = linesize;
                        lObj05.name = "side"; //名前
                        lObj05.selected = true;
                        lObj07= activeDocument.pathItems.add();
                        lObj07.setEntirePath([[p9x,p9y],[p7x,p7y]]);
                        lObj07.filled = false; // 塗りなし
                        lObj07.stroked = true; // 線あり
                        lObj07.strokeColor= lineColorG; //色指定
                        lObj07.strokeWidth = linesize;
                        lObj07.name = "side"; //名前
                        lObj07.selected = true;
                        app.executeMenuCommand("join");
                        app.executeMenuCommand("deselectall");
                        lObj02 = activeDocument.pathItems.add();
                        lObj02.setEntirePath([[p1x+(p2x-p1x)*2,p1y],[p3x+(p4x-p3x)*2,p3y]]);
                        lObj02.filled = false; // 塗りなし
                        lObj02.stroked = true; // 線あり
                        lObj02.strokeColor= lineColorP; //色指定
                        lObj02.strokeWidth = linesize;
                        lObj02.name = "side"; //名前
                        lObj02.selected = true;
                        lObj04 = activeDocument.pathItems.add();
                        lObj04.setEntirePath([[p3x+(p4x-p3x)*2,p3y],[p5x+(p6x-p5x)*2,p5y]]);
                        lObj04.filled = false; // 塗りなし
                        lObj04.stroked = true; // 線あり
                        lObj04.strokeColor= lineColorP; //色指定
                        lObj04.strokeWidth = linesize;
                        lObj04.name = "side"; //名前
                        lObj04.selected = true;
                        lObj06 = activeDocument.pathItems.add();
                        lObj06.setEntirePath([[p7x+(p8x-p7x)*2,p7y],[p5x+(p6x-p5x)*2,p5y]]);
                        lObj06.filled = false; // 塗りなし
                        lObj06.stroked = true; // 線あり
                        lObj06.strokeColor= lineColorP; //色指定
                        lObj06.strokeWidth = linesize;
                        lObj06.name = "side"; //名前
                        lObj06.selected = true;
                        lObj08 = activeDocument.pathItems.add();
                        lObj08.setEntirePath([[p9x+(p10x-p9x)*2,p9y],[p7x+(p8x-p7x)*2,p7y]]);
                        lObj08.filled = false; // 塗りなし
                        lObj08.stroked = true; // 線あり
                        lObj08.strokeColor= lineColorP; //色指定
                        lObj08.strokeWidth = linesize;
                        lObj08.name = "side"; //名前
                        lObj08.selected = true;
                        app.executeMenuCommand("join");
                        app.executeMenuCommand("deselectall");
                    }
                }
                else{
                    //サイド角が二ある場合
                    var p3x = sel[i+1].pathPoints[0].anchor[0]; 
                    var p3y = sel[i+1].pathPoints[0].anchor[1];
                    var p4x = sel[i+1].pathPoints[1].anchor[0];
                    var p4y = sel[i+1].pathPoints[1].anchor[1];
                    var p5x = sel[i+2].pathPoints[0].anchor[0]; 
                    var p5y = sel[i+2].pathPoints[0].anchor[1];
                    var p6x = sel[i+2].pathPoints[1].anchor[0];
                    var p6y = sel[i+2].pathPoints[1].anchor[1];
                    var p7x = sel[i+3].pathPoints[0].anchor[0]; 
                    var p7y = sel[i+3].pathPoints[0].anchor[1];
                    var p8x = sel[i+3].pathPoints[1].anchor[0];
                    var p8y = sel[i+3].pathPoints[1].anchor[1];
                    app.executeMenuCommand("deselectall");
                    lObj01 = activeDocument.pathItems.add();
                    lObj01.setEntirePath([[p1x,p1y],[p3x,p3y]]);
                    lObj01.filled = false; // 塗りなし
                    lObj01.stroked = true; // 線あり
                    lObj01.strokeColor= lineColorG; //色指定
                    lObj01.strokeWidth = linesize;
                    lObj01.name = "side"; //名前
                    lObj01.selected = true;
                    lObj03 = activeDocument.pathItems.add();
                    lObj03.setEntirePath([[p3x,p3y],[p5x,p5y]]);
                    lObj03.filled = false; // 塗りなし
                    lObj03.stroked = true; // 線あり
                    lObj03.strokeColor= lineColorG; //色指定
                    lObj03.strokeWidth = linesize;
                    lObj03.name = "side"; //名前
                    lObj03.selected = true;
                    lObj05= activeDocument.pathItems.add();
                    lObj05.setEntirePath([[p7x,p7y],[p5x,p5y]]);
                    lObj05.filled = false; // 塗りなし
                    lObj05.stroked = true; // 線あり
                    lObj05.strokeColor= lineColorG; //色指定
                    lObj05.strokeWidth = linesize;
                    lObj05.name = "side"; //名前
                    lObj05.selected = true;
                    app.executeMenuCommand("join");
                    app.executeMenuCommand("deselectall");
                    lObj02 = activeDocument.pathItems.add();
                    lObj02.setEntirePath([[p1x+(p2x-p1x)*2,p1y],[p3x+(p4x-p3x)*2,p3y]]);
                    lObj02.filled = false; // 塗りなし
                    lObj02.stroked = true; // 線あり
                    lObj02.strokeColor= lineColorP; //色指定
                    lObj02.strokeWidth = linesize;
                    lObj02.name = "side"; //名前
                    lObj02.selected = true;
                    lObj04 = activeDocument.pathItems.add();
                    lObj04.setEntirePath([[p3x+(p4x-p3x)*2,p3y],[p5x+(p6x-p5x)*2,p5y]]);
                    lObj04.filled = false; // 塗りなし
                    lObj04.stroked = true; // 線あり
                    lObj04.strokeColor= lineColorP; //色指定
                    lObj04.strokeWidth = linesize;
                    lObj04.name = "side"; //名前
                    lObj04.selected = true;
                    lObj06 = activeDocument.pathItems.add();
                    lObj06.setEntirePath([[p7x+(p8x-p7x)*2,p7y],[p5x+(p6x-p5x)*2,p5y]]);
                    lObj06.filled = false; // 塗りなし
                    lObj06.stroked = true; // 線あり
                    lObj06.strokeColor= lineColorP; //色指定
                    lObj06.strokeWidth = linesize;
                    lObj06.name = "side"; //名前
                    lObj06.selected = true;
                    app.executeMenuCommand("join");
                    app.executeMenuCommand("deselectall");
                }
            }
            else{
                //サイド線が一回曲がる場合
                var p3x = sel[i+1].pathPoints[0].anchor[0]; 
                var p3y = sel[i+1].pathPoints[0].anchor[1];
                var p4x = sel[i+1].pathPoints[1].anchor[0];
                var p4y = sel[i+1].pathPoints[1].anchor[1];
                var p5x = sel[i+2].pathPoints[0].anchor[0]; 
                var p5y = sel[i+2].pathPoints[0].anchor[1];
                var p6x = sel[i+2].pathPoints[1].anchor[0];
                var p6y = sel[i+2].pathPoints[1].anchor[1];
                app.executeMenuCommand("deselectall");
                lObj01 = activeDocument.pathItems.add();
                lObj01.setEntirePath([[p1x,p1y],[p3x,p3y]]);
                lObj01.filled = false; // 塗りなし
                lObj01.stroked = true; // 線あり
                lObj01.strokeColor= lineColorG; //色指定
                lObj01.strokeWidth = linesize;
                lObj01.name = "side"; //名前
                lObj01.selected = true;
                lObj03= activeDocument.pathItems.add();
                lObj03.setEntirePath([[p3x,p3y],[p5x,p5y]]);
                lObj03.filled = false; // 塗りなし
                lObj03.stroked = true; // 線あり
                lObj03.strokeColor= lineColorG; //色指定
                lObj03.strokeWidth = linesize;
                lObj03.name = "side"; //名前
                lObj03.selected = true;
                app.executeMenuCommand("join");
                app.executeMenuCommand("deselectall");
                lObj02 = activeDocument.pathItems.add();
                lObj02.setEntirePath([[p1x+(p2x-p1x)*2,p1y],[p3x+(p4x-p3x)*2,p3y]]);
                lObj02.filled = false; // 塗りなし
                lObj02.stroked = true; // 線あり
                lObj02.strokeColor= lineColorP; //色指定
                lObj02.strokeWidth = linesize;
                lObj02.name = "side"; //名前
                lObj02.selected = true;
                lObj04 = activeDocument.pathItems.add();
                lObj04.setEntirePath([[p3x+(p4x-p3x)*2,p3y],[p5x+(p6x-p5x)*2,p5y]]);
                lObj04.filled = false; // 塗りなし
                lObj04.stroked = true; // 線あり
                lObj04.strokeColor= lineColorP; //色指定
                lObj04.strokeWidth = linesize;
                lObj04.name = "side"; //名前
                lObj04.selected = true;
                app.executeMenuCommand("join");
                app.executeMenuCommand("deselectall");
            }
        }
        else{
            //サイド線が一直線の場合
            var p3x = sel[i+1].pathPoints[0].anchor[0]; 
            var p3y = sel[i+1].pathPoints[0].anchor[1];
            var p4x = sel[i+1].pathPoints[1].anchor[0];
            var p4y = sel[i+1].pathPoints[1].anchor[1];
            app.executeMenuCommand("deselectall");
            lObj01 = activeDocument.pathItems.add();
            lObj01.setEntirePath([[p1x,p1y],[p3x,p3y]]);
            lObj01.filled = false; // 塗りなし
            lObj01.stroked = true; // 線あり
            lObj01.strokeColor= lineColorG; //色指定
            lObj01.strokeWidth = linesize;
            lObj01.name = "side"; //名前
            lObj01.selected = false;
            lObj02 = activeDocument.pathItems.add();
            lObj02.setEntirePath([[p1x+(p2x-p1x)*2,p1y],[p3x+(p4x-p3x)*2,p3y]]);
            lObj02.filled = false; // 塗りなし
            lObj02.stroked = true; // 線あり
            lObj02.strokeColor= lineColorP; //色指定
            lObj02.strokeWidth = linesize;
            lObj02.name = "side"; //名前
            lObj02.selected = false;
            app.executeMenuCommand("deselectall");
            }
        }
    }

//レンズ面の描写
selchangecolorB();
sel = activeDocument.selection;
for (var i = 0; i < sel.length; i++){
// 線iの座標を取得
var p1x = sel[i].pathPoints[0].anchor[0];
var p1y = sel[i].pathPoints[0].anchor[1];
var p2x = sel[i].pathPoints[1].anchor[0];
var p2y = sel[i].pathPoints[1].anchor[1];
// 円を描く
    if (p1y==p2y){
        lObj = activeDocument.pathItems.add();
        lObj.setEntirePath([[p1x,p1y],[p1x+(p2x-p1x)*2,p2y]]);
        lObj.filled = false; // 塗りなし
        lObj.stroked = true; // 線あり
        lObj.strokeColor= lineColorB;
        lObj.strokeWidth = linesize;
        lObj.selected = true; //選択する
        
        if (sel[i].name=="lensTop"){ 
            lObj.name = "lensTop";
        }
        else{  
            lObj.name = "lensRear";
        }
        sel[i].remove();
        }
    else{
        c = (p2x-p1x)*2; // 弦長
        cr = (p2x-p1x);
        h = Math.abs(p2y-p1y); // 矢高
        r = ((c*c)+(4*(h*h)))/(8*h);// 半径
        p1y2 = Math.abs(p1y);//めんどいから実数
        p2y2 = Math.abs(p2y);//上に同じ
        dx=p2x-p1x;//下で使う用
        dy=p2y2-p1y2;//上に同じ
        angle = Math.atan2(dy, dx);
        angleh = angle/(Math.PI/4);
        pathG1 = r*0.55229;
        pathG = Math.abs(angleh*pathG1);
        a=p1x+cr-pathG;
        b=p1x+cr+pathG;
        x=pathG* Math.cos(angle*2);
        y=pathG* Math.sin(angle*2);
        pObj01 = activeDocument.pathItems.add();
        pObj01.filled = false; //　塗りなし
        pObj01.stroked = true; //　線あり
        pObj01.strokeColor= lineColorB;
        pObj01.strokeWidth = linesize;
        nPathObj = pObj01.pathPoints.add();
        nPathObj.anchor = [p1x,p1y];
        nPathObj.leftDirection = [p1x+x,p1y-y];
        nPathObj.rightDirection = [p1x+x,p1y-y];
        nPathObj.pointType = PointType.SMOOTH;
        nPathObj = pObj01.pathPoints.add();
        nPathObj.anchor = [p2x,p2y];
        nPathObj.leftDirection = [a,p2y];
        nPathObj.rightDirection = [b,p2y];
        nPathObj.pointType = PointType.SMOOTH;
        nPathObj = pObj01.pathPoints.add();
        nPathObj.anchor = [p1x+c,p1y];
        nPathObj.leftDirection = [p1x+c-x,p1y-y];
        nPathObj.rightDirection = [p1x+c-x,p1y-y];
        nPathObj.pointType = PointType.SMOOTH;
        
        if (sel[i].name=="lensTop"){
            pObj01.name = "lensTop";
        }
        else{  
            pObj01.name = "lensRear";
        }
        sel[i].remove();  
    }
}

//赤線削除
selchangecolorR()
sel = activeDocument.selection;
for (var i = 0; i < sel.length; i++){
    sel[i].remove();
}

//レンズ毎に結合
selchangecolorB();
sel1 = activeDocument.selection;
for (var i = 0; i < sel1.length; i++){
if(sel1[i].name=="lensRear"){

    var p1x = sel1[i].pathPoints[0].anchor[0];
    var p1y = sel1[i].pathPoints[0].anchor[1];
    var p2x = sel1[i].pathPoints[1].anchor[0];
    var p2y = sel1[i].pathPoints[1].anchor[1];
    selchangecolorG();
    sel2 = activeDocument.selection;
    for (var j = 0; j < sel2.length; j++){
        var p3x = sel2[j].pathPoints[0].anchor[0];
        var p3y = sel2[j].pathPoints[0].anchor[1];
        var p4x = sel2[j].pathPoints[1].anchor[0];
        var p4y = sel2[j].pathPoints[1].anchor[1];
        if( (p1x==p3x && p1y==p3y)||(p1x==p4x && p1y==p4y)||(p2x==p3x && p2y==p3y)||(p2x==p4x && p2y==p4y)){
            app.executeMenuCommand("deselectall");
            sel1[i].selected = true;
            sel2[j].selected = true;
            app.executeMenuCommand("join");
            app.executeMenuCommand("deselectall");
            }
        }
    }
}

selchangecolorB();
sel1 = activeDocument.selection;
for (var i = 0; i < sel1.length; i++){
if(sel1[i].name=="lensRear"){

    var p1x = sel1[i].pathPoints[0].anchor[0];
    var p1y = sel1[i].pathPoints[0].anchor[1];
    var p2x = sel1[i].pathPoints[1].anchor[0];
    var p2y = sel1[i].pathPoints[1].anchor[1];
    selchangecolorP();
    sel3 = activeDocument.selection;
    for (var k = 0; k < sel3.length; k++){
        var p5x = sel3[k].pathPoints[0].anchor[0];
        var p5y = sel3[k].pathPoints[0].anchor[1];
        var p6x = sel3[k].pathPoints[1].anchor[0];
        var p6y = sel3[k].pathPoints[1].anchor[1];
        if( (p1x==p5x && p1y==p5y)||(p1x==p6x && p1y==p6y)||(p2x==p5x && p2y==p5y)||(p2x==p6x && p2y==p6y) ){
            app.executeMenuCommand("deselectall");
            sel1[i].selected = true;
            sel3[k].selected = true;
            app.executeMenuCommand("join");
            app.executeMenuCommand("deselectall");
            }
        }
    }
}

selchangecolorB();
sel1 = activeDocument.selection;
for (var i = 0; i < sel1.length; i++){
if(sel1[i].name=="lensRear"){

    var p1x = sel1[i].pathPoints[0].anchor[0];
    var p1y = sel1[i].pathPoints[0].anchor[1];
    var p2x = sel1[i].pathPoints[1].anchor[0];
    var p2y = sel1[i].pathPoints[1].anchor[1];
    selchangecolorB();
    sel2 = activeDocument.selection;
    for (var j = 0; j < sel2.length; j++){
        if(sel2[j].name=="lensTop"){
            var p3x = sel2[j].pathPoints[0].anchor[0];
            var p3y = sel2[j].pathPoints[0].anchor[1];
            var p4x = sel2[j].pathPoints[1].anchor[0];
            var p4y = sel2[j].pathPoints[1].anchor[1];
            if( (p1x==p3x && p1y==p3y)||(p1x==p4x && p1y==p4y)||(p2x==p3x && p2y==p3y)||(p2x==p4x && p2y==p4y) ){
                app.executeMenuCommand("deselectall");
                sel1[i].selected = true;
                sel2[j].selected = true;
                app.executeMenuCommand("join");
                app.executeMenuCommand("deselectall");
                }
            }
        }
    }
}
