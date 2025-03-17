<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>EditCACSCT</title>
    <link href="/Content/bootstrap.min.css" rel="stylesheet" />
    <link href="/Content/bootstrap-theme.css" rel="stylesheet" />
    <link href="/Content/font-awesome.min.css" rel="stylesheet" />
    <link href="/Content/jquery.loadmask.css" rel="stylesheet">
    <link href="/Content/css?v=ji3nO1pdg6VLv3CVUWntxgZNf1zRciWDbm4YfW-y0RI1" rel="stylesheet"/>

    <script src="/bundles/modernizr?v=qVODBytEBVVePTNtSFXgRX0NCEjh9U_Oj8ePaSiRcGg1"></script>

    <script src="/bundles/jquery?v=aVgyEaZfAxZS60CT-VlCELEfaJJd3gsmIEC_bIC2LQQ1"></script>

</head>
<body>
    
<div class="divBody">
    <!--NAV BAR-->
    <ul class="nav nav-pills">
      <li>
        <div class="to_Home">
            <a onclick="toHome();" class="btn btn-info"><i class="fa fa-home"></i>Home</a>
        </div>
      </li>
      <li>
        <div class="save_btn">
            <a onclick="savedata();" class="btn btn-success"><i class="fa fa-floppy-o"></i>儲存</a>
        </div>
      </li>  
    </ul>
    <!--NAV BAR-->
 
    <div class="panel panel-success">
        <div class="panel-heading">
            <h3 class="panel-title">基本資料</h3>
        </div>
        <div class="panel-body">
            <div class="col-md-6">
                <ul class="PatientsInfo_left">
                    <li><span>檢查日期：</span><span>1140317</span></li>
                    <li><span>貴賓姓名：</span><span>郭秋杏</span></li>
                    <li><span>病歷號碼：</span><span>11490487</span></li>  
                </ul>
            </div>
            <div class="col-md-6">
                <ul class="PatientsInfo_Right">
                    <li><span>性別：</span><span>女</span></li>    
                    <li><span>生日：</span><span>0460909</span></li>    
                    <li><span>年齡：</span><span>68</span></li>    
                </ul>
            </div>
        </div>
    </div>

    <h2>影像發現:</h2>

    <div class="alert-info" role="alert"><span class="glyphicon glyphicon-list"></span>預覽：</div>
    <div id="Preview" class="panel panel-info">
        <ul id="PreviewUl" >

            
        </ul>
        <ul>
            <li style='list-style-type: none;'>
                <a class="btn btn-default btn-xs" href="javascript: AddNewItem();"><span class='glyphicon glyphicon-plus'>新增清單項目</span></a>
                <a class="btn btn-danger btn-xs" href="javascript: ClearItem();"><span class='glyphicon glyphicon-remove'>清除所有項目</span></a>
            </li>
        </ul> 
        <ul id="ArteryCalciumAdvice" class="previewtopline"></ul> 
        <ul id="ArteriesAnalysisAdvice" class="previewtopline"></ul> 
        <div id="tempList">
        


        </div>
    </div>

    <h2>總結:<label for="NormalResult" class="NormalResult" onclick="NormalResult();"><input type="checkbox" id="NormalResult" /><span>設定總結為無異常</span></label></h2>
    <div class="panel panel-info">
        <ul id="PreviewAbnormal"></ul>
        <ul id="PreviewAbnormalAAA"></ul>
    </div>
    <div id="EditArea">
        <button class="btn btn-default Editor_Btn" id="OpenEditor"><i class="fa fa-circle-o"></i>開啟編輯</button>
        <button class="btn btn-default Editor_Btn" id="OpenEditorIng" style="display:none"><i class="fa fa-spinner fa-spin"></i>開啟編輯</button>
        <button class="btn btn-default Editor_Btn" id="CloseEditor" style="display:none"><i class="fa fa-times"></i>關閉編輯</button>
        
    </div>

    <h2>建議與追蹤處置:</h2>
    <div id="Advice">

        <ul>
            <li>
                <label class="AdviceItem" for="AdviceItem1">
                    <input type="checkbox" id="AdviceItem1" value="建議定期追蹤。" /><span>建議定期追蹤。</span>
                </label>
            </li>
            <li>
                <label class="AdviceItem" for="AdviceItem2">
                    <input type="checkbox" id="AdviceItem2" value="建議心臟科門診追蹤。"  /><span>建議心臟科門診追蹤。</span>
                </label>
            </li>
            <li>
                <label class="AdviceItem" for="AdviceItem3">
                    <input type="checkbox" id="AdviceItem3" value="建議心臟科門診評估治療。"  /><span>建議心臟科門診評估治療。</span>
                </label>
            </li>
            <li>
                <label class="AdviceItem" for="AdviceItem4">
                    <input type="checkbox" id="AdviceItem4" value="無特異性異常發現，請定期追蹤。"  /><span>無特異性異常發現，請定期追蹤。</span>
                </label>
            </li>
            <li>
                <p>其他：</p>
                <textarea></textarea>
            </li>
        </ul>
    </div>
    <div id="Doctor"><span>報告醫師：</span><span>謝立群</span></div>

    <div><span class="glyphicon glyphicon-th-list SubItem_title_icon"></span>附加圖片</div>
    <div id="PhotoField">
        <ul id="AdvicePhotoList" class="PhotoList">

        </ul>
    </div>
    <!--分頁線-->
    <div style="height: 2px; background-color: black; text-align: center">
        <span style="background-color: white; position: relative; top: -0.5em;">分頁線</span>
    </div><br>
    <!--分頁線-->  

    <div class="IncludeTable">
        <p>
            高階電腦斷層冠狀動脈鈣化指數分析
            (Coronary artery calcium score)
        </p>
        <table border="1" class="Artery_Table">
	        <tr>
		        <td>項次</td>
		        <td colspan="2">心臟血管解剖部位名稱</td>
		        <td colspan="2">醫學影像判讀結果</td>
	        </tr>
	        <tr>
		        <td>No.</td>
		        <td>中文名稱</td>
		        <td>英文名稱</td>
		        <td>指數(Score)</td>
		        <td>請見特別說明欄</td>
	        </tr>
	        <tr>
		        <td>&nbsp;</td>
		        <td>冠狀動脈</td>
		        <td>Coronary artery</td>
		        <td>&nbsp;</td>
		        <td>&nbsp;</td>
	        </tr>
	        <tr>
		        <td>9.30</td>
		        <td>左主冠狀動脈</td>
		        <td>Left Main Artery,LMA</td>
		        <td>

                    <div id="LMA_Score" contenteditable="true" onkeyup="checkval($(this));">0</div>
		        </td>
		        <td><div id="LMA_Explain" contenteditable="true"></div></td>
	        </tr>
	        <tr>
		        <td>9.31</td>
		        <td>左前降冠狀動脈</td>
		        <td>Left anterior descending,LAD</td>
		        <td>

                    <div id="LAD_Score" contenteditable="true" onkeyup="checkval($(this));">0</div>
		        </td>
		        <td><div id="LAD_Explain" contenteditable="true"></div></td>
	        </tr>
	        <tr>
		        <td>9.31</td>
		        <td>左迴旋冠狀動脈</td>
		        <td>Left circumflex,LCX</td>
		        <td>

                    <div id="LCX_Score" contenteditable="true" onkeyup="checkval($(this));">0</div>
		        </td>
		        <td><div id="LCX_Explain" contenteditable="true"></div></td>
	        </tr>
	        <tr>
		        <td>9.41</td>
		        <td>右冠狀動脈</td>
		        <td>Right coronary artery,RCA</td>
		        <td>

                    <div id="RCA_Score" contenteditable="true" onkeyup="checkval($(this));">0</div>
		        </td>
		        <td><div id="RCA_Explain" contenteditable="true"></div></td>
	        </tr>
	        <tr>
		        <td>&nbsp;</td>
		        <td>總分</td>
		        <td>Total</td>
		        <td>

                    <div id="Total_Score" contenteditable="true" onkeyup="checkval($(this));">0</div>
		        </td>
		        <td><div id="Total_Explain" contenteditable="true"></div></td>
	        </tr>
	        <tr>
                <td colspan="5">YOUR CORONARY ARTERY CALCIUM SCORE IS
 
                    <span id="Calcium_Score" class="Calcium_Score" contenteditable="true">0</span>
                </td>
	        </tr>
	        <tr>
                <td colspan="5">您的冠狀動脈鈣化指數為
                    <span id="Calcium_Score_CN" class="Calcium_Score" contenteditable="true">0</span>
                </td>
	        </tr>
            </table>
	        <table class="table-add">     <tbody><tr><td>鈣化總積分</td><td>0~10</td><td>11~100</td><td>101~400</td><td>&gt;400</td></tr>    <tr><td>動脈硬化斑塊程度</td><td>無或微量</td><td>輕度</td><td>中度</td><td>廣泛性</td></tr></tbody></table>
            <p>註：高階電腦斷層冠狀動脈鈣化指數會有小數點後第兩位數值的些微差異，但不影響您的鈣化分級。</p>
    </div>
    <br>
    <!--分頁線-->
    <div style="height: 2px; background-color: black; text-align: center">
        <span style="background-color: white; position: relative; top: -0.5em;">分頁線</span>
    </div><br>
    <!--分頁線-->
    <div  class="IncludeTable">
        <p>高階電腦斷層冠狀動脈攝影(Coronary CT angiography)</p>
        <form id="FORM_CT">
            <input type="hidden" name="ACCESSNO" value="341606165 " />
            <input type="hidden" name="CHECK_PROJECT" value="CACSCT" />
            <input type="hidden" name="CNO" value="11490487" />
            <input type="hidden" name="MODIFIED_STAFF" value=" " />
            <table border="1" class="CT_table">
		        <tr>
			        <td>冠狀動脈顯要性</td>
			        <td>
				        <div>

					        <label for="RT_dominant">
                                <input type="checkbox" id="RT_dominant" name="RT_dominant" class="dominant"  /><span>右側顯要(Rt dominant)(RCA→PDA,PLA)</span>
					        </label>
				        </div>
				        <div>

					        <label for="CO_dominant">
                                <input type="checkbox" id="CO_dominant" name="CO_dominant" class="dominant"  /><span>共同顯要(Co dominant)(RCA→PDA,LCA→PLA)</span>
					        </label>
				        </div>
				        <div>

					        <label for="LT_dominant">
                                <input type="checkbox" id="LT_dominant" name="LT_dominant" class="dominant"  /><span>左側顯要(Lt dominant)(LCA→PLA,PDA)</span>
					        </label>
				        </div>
			        </td>
		        </tr>

		        
	        </table>
        </form>
	    <img src="/Content/img/CoronaryCT.png"/>
	    <div>
           <!--
		    右冠狀動脈(RCA)：近側端(1)、中段(2)、遠側端(3)、PDA(4)、R-PLB(16)<br> 
		    左冠狀動脈(LCA)之左主枝(LM)(5)<br>
		    左冠狀動脈前下行枝(LAD)：前段(6)、中段(7)、遠側端(8)、D1(9)、D2(10)；<br>
		    中間枝(RI)(17)；<br>
		    左冠狀動脈左迴旋枝(LCX)：前段(11)、OM1(12)、遠側端(13)、OM2(14)、PDA(15)、L-PLB(18)                
                -->
            (1) 右冠狀動脈 (Right Coronary Artery, RCA) 近側端，(2) 右冠狀動脈 (RCA) 中段<br> 
            ，(3) 右冠狀動脈 (RCA) 遠側端，(4) 右冠狀動脈 (RCA) 之後降動脈 (PDA)，<br>
            (5) 左冠狀動脈 (Left Coronary Artery, LCA) 之左主枝 (LM)，<br>
            (6) 左冠狀動脈之前下降枝 (Left Anterior Descending Artery, LAD) 近側端，<br>
            (7) 左冠狀動脈之前下降枝 (LAD) 中段，(8) 左冠狀動脈之前下降枝 (LAD) 遠側端，<br>
            (9) 左冠狀動脈前下降枝 (LAD) 第一對角動脈 (First Diagonal Artery, D1)，<br>
            (10) 左冠狀動脈前下降枝 (LAD) 第二對角動脈 (Second Diagonal Artery, D2)，<br>
            (11) 左冠狀動脈迴旋枝 (Left Circumflex Artery, LCX) 近側端，<br>
            (12) 左冠狀動脈迴旋枝 (LCX) 第一鈍緣分枝 (First Obtuse Marginal Artery, OM1)，<br>
            (13) 左冠狀動脈迴旋枝 (LCX) 遠側端，<br>
            (14) 左冠狀動脈迴旋枝 (LCX) 第二鈍緣分枝 (Second Obtuse Marginal Artery, OM2)，<br>
            (15) 左冠狀動脈迴旋枝 (LCX) 之後降動脈 (PDA)，<br>
            (16) 右冠狀動脈 (RCA) 後側分枝(Posterio-lateral, R-PLB)，(17) 中間支 (Ramus Intermedius Artery, RI)，<br>
            (18) 左冠狀動脈迴旋枝 (LCX) 之後側分枝 (Posterio-lateral, L-PLB)。
             

	    </div>
    </div>
    <!--分頁線-->
    <div style="height: 2px; background-color: black; text-align: center">
        <span style="background-color: white; position: relative; top: -0.5em;">分頁線</span>
    </div><br>
    <!--分頁線-->
    <div id="ArteriesForm">
        <button class="btn btn-default" onclick="DefaultChecked();"><i class="fa fa-check-square-o"></i>全部管腔直徑正常無狹窄</button>
        <table border="1" class="ArteriesTable">
	    <tr>
		    <td>&nbsp;</td><td>&nbsp;</td><td colspan="3">斑塊</td>
		    <td rowspan="2">管腔直徑正常無狹窄</td>
		    <td rowspan="2">管腔直徑狹窄&lt;25%</td>
		    <td rowspan="2">管腔直徑狹窄25-49%</td>
		    <td rowspan="2">管腔直徑狹窄50-69%</td>
		    <td rowspan="2">管腔直徑狹窄70-99%</td>
            <td rowspan="2">管腔直徑完全阻塞</td>
		    <td rowspan="2">此血管口徑細小或不明顯</td>
		    <td rowspan="2">備註</td>
	    </tr>
	    <tr>
		    <td>&nbsp;</td>
		    <td>&nbsp;</td>
		    <td>非鈣化<br>(non-  calcified plaque)</td>
		    <td>鈣化<br>(calcified plaque)</td>
		    <td>複合性鈣化<br>(partially calcified plaque)</td>	
	    </tr>
	    <tr>
		    <td rowspan="5">右冠狀動脈(RCA)分析</td>
		    <td>近側端(1)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_1' name='Subject_No' value='1' />	<label for='NonCP_1'>		<input type='checkbox' id='NonCP_1' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_1'>		<input type='checkbox' id='CP_1' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_1'>		<input type='checkbox' id='PCP_1' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_1'>		<input type='checkbox' id='LD_0_1' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_1'>		<input type='checkbox' id='LD_Less25_1' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_1'>		<input type='checkbox' id='LD_25to49_1' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_1'>		<input type='checkbox' id='LD_50to69_1' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_1'>		<input type='checkbox' id='LD_70to99_1' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_1'>		<input type='checkbox' id='LD_100_1' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_1'>		<input type='checkbox' id='NotObvious_1' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_1' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>中段(2)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_2' name='Subject_No' value='2' />	<label for='NonCP_2'>		<input type='checkbox' id='NonCP_2' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_2'>		<input type='checkbox' id='CP_2' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_2'>		<input type='checkbox' id='PCP_2' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_2'>		<input type='checkbox' id='LD_0_2' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_2'>		<input type='checkbox' id='LD_Less25_2' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_2'>		<input type='checkbox' id='LD_25to49_2' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_2'>		<input type='checkbox' id='LD_50to69_2' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_2'>		<input type='checkbox' id='LD_70to99_2' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_2'>		<input type='checkbox' id='LD_100_2' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_2'>		<input type='checkbox' id='NotObvious_2' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_2' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>遠側端(3)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_3' name='Subject_No' value='3' />	<label for='NonCP_3'>		<input type='checkbox' id='NonCP_3' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_3'>		<input type='checkbox' id='CP_3' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_3'>		<input type='checkbox' id='PCP_3' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_3'>		<input type='checkbox' id='LD_0_3' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_3'>		<input type='checkbox' id='LD_Less25_3' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_3'>		<input type='checkbox' id='LD_25to49_3' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_3'>		<input type='checkbox' id='LD_50to69_3' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_3'>		<input type='checkbox' id='LD_70to99_3' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_3'>		<input type='checkbox' id='LD_100_3' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_3'>		<input type='checkbox' id='NotObvious_3' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_3' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>PDA(4)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_4' name='Subject_No' value='4' />	<label for='NonCP_4'>		<input type='checkbox' id='NonCP_4' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_4'>		<input type='checkbox' id='CP_4' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_4'>		<input type='checkbox' id='PCP_4' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_4'>		<input type='checkbox' id='LD_0_4' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_4'>		<input type='checkbox' id='LD_Less25_4' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_4'>		<input type='checkbox' id='LD_25to49_4' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_4'>		<input type='checkbox' id='LD_50to69_4' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_4'>		<input type='checkbox' id='LD_70to99_4' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_4'>		<input type='checkbox' id='LD_100_4' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_4'>		<input type='checkbox' id='NotObvious_4' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_4' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>R-PLB(16)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_16' name='Subject_No' value='16' />	<label for='NonCP_16'>		<input type='checkbox' id='NonCP_16' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_16'>		<input type='checkbox' id='CP_16' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_16'>		<input type='checkbox' id='PCP_16' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_16'>		<input type='checkbox' id='LD_0_16' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_16'>		<input type='checkbox' id='LD_Less25_16' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_16'>		<input type='checkbox' id='LD_25to49_16' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_16'>		<input type='checkbox' id='LD_50to69_16' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_16'>		<input type='checkbox' id='LD_70to99_16' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_16'>		<input type='checkbox' id='LD_100_16' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_16'>		<input type='checkbox' id='NotObvious_16' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_16' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>左冠狀動脈(LCA)分析</td>
		    <td>左主枝(LM)(5)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_5' name='Subject_No' value='5' />	<label for='NonCP_5'>		<input type='checkbox' id='NonCP_5' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_5'>		<input type='checkbox' id='CP_5' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_5'>		<input type='checkbox' id='PCP_5' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_5'>		<input type='checkbox' id='LD_0_5' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_5'>		<input type='checkbox' id='LD_Less25_5' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_5'>		<input type='checkbox' id='LD_25to49_5' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_5'>		<input type='checkbox' id='LD_50to69_5' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_5'>		<input type='checkbox' id='LD_70to99_5' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_5'>		<input type='checkbox' id='LD_100_5' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_5'>		<input type='checkbox' id='NotObvious_5' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_5' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td rowspan="5">左冠狀動脈前下行枝(LAD)分析</td>
		    <td>前段(6)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_6' name='Subject_No' value='6' />	<label for='NonCP_6'>		<input type='checkbox' id='NonCP_6' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_6'>		<input type='checkbox' id='CP_6' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_6'>		<input type='checkbox' id='PCP_6' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_6'>		<input type='checkbox' id='LD_0_6' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_6'>		<input type='checkbox' id='LD_Less25_6' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_6'>		<input type='checkbox' id='LD_25to49_6' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_6'>		<input type='checkbox' id='LD_50to69_6' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_6'>		<input type='checkbox' id='LD_70to99_6' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_6'>		<input type='checkbox' id='LD_100_6' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_6'>		<input type='checkbox' id='NotObvious_6' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_6' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>中段(7)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_7' name='Subject_No' value='7' />	<label for='NonCP_7'>		<input type='checkbox' id='NonCP_7' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_7'>		<input type='checkbox' id='CP_7' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_7'>		<input type='checkbox' id='PCP_7' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_7'>		<input type='checkbox' id='LD_0_7' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_7'>		<input type='checkbox' id='LD_Less25_7' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_7'>		<input type='checkbox' id='LD_25to49_7' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_7'>		<input type='checkbox' id='LD_50to69_7' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_7'>		<input type='checkbox' id='LD_70to99_7' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_7'>		<input type='checkbox' id='LD_100_7' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_7'>		<input type='checkbox' id='NotObvious_7' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_7' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>遠側端(8)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_8' name='Subject_No' value='8' />	<label for='NonCP_8'>		<input type='checkbox' id='NonCP_8' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_8'>		<input type='checkbox' id='CP_8' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_8'>		<input type='checkbox' id='PCP_8' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_8'>		<input type='checkbox' id='LD_0_8' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_8'>		<input type='checkbox' id='LD_Less25_8' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_8'>		<input type='checkbox' id='LD_25to49_8' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_8'>		<input type='checkbox' id='LD_50to69_8' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_8'>		<input type='checkbox' id='LD_70to99_8' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_8'>		<input type='checkbox' id='LD_100_8' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_8'>		<input type='checkbox' id='NotObvious_8' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_8' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>D1(9)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_9' name='Subject_No' value='9' />	<label for='NonCP_9'>		<input type='checkbox' id='NonCP_9' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_9'>		<input type='checkbox' id='CP_9' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_9'>		<input type='checkbox' id='PCP_9' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_9'>		<input type='checkbox' id='LD_0_9' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_9'>		<input type='checkbox' id='LD_Less25_9' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_9'>		<input type='checkbox' id='LD_25to49_9' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_9'>		<input type='checkbox' id='LD_50to69_9' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_9'>		<input type='checkbox' id='LD_70to99_9' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_9'>		<input type='checkbox' id='LD_100_9' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_9'>		<input type='checkbox' id='NotObvious_9' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_9' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>D2(10)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_10' name='Subject_No' value='10' />	<label for='NonCP_10'>		<input type='checkbox' id='NonCP_10' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_10'>		<input type='checkbox' id='CP_10' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_10'>		<input type='checkbox' id='PCP_10' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_10'>		<input type='checkbox' id='LD_0_10' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_10'>		<input type='checkbox' id='LD_Less25_10' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_10'>		<input type='checkbox' id='LD_25to49_10' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_10'>		<input type='checkbox' id='LD_50to69_10' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_10'>		<input type='checkbox' id='LD_70to99_10' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_10'>		<input type='checkbox' id='LD_100_10' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_10'>		<input type='checkbox' id='NotObvious_10' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_10' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>中間枝(RI)分析</td>
		    <td>第17段</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_17' name='Subject_No' value='17' />	<label for='NonCP_17'>		<input type='checkbox' id='NonCP_17' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_17'>		<input type='checkbox' id='CP_17' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_17'>		<input type='checkbox' id='PCP_17' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_17'>		<input type='checkbox' id='LD_0_17' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_17'>		<input type='checkbox' id='LD_Less25_17' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_17'>		<input type='checkbox' id='LD_25to49_17' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_17'>		<input type='checkbox' id='LD_50to69_17' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_17'>		<input type='checkbox' id='LD_70to99_17' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_17'>		<input type='checkbox' id='LD_100_17' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_17'>		<input type='checkbox' id='NotObvious_17' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_17' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td rowspan="6">左冠狀動脈左迴旋枝(LCX)分析</td>
		    <td>前段(11)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_11' name='Subject_No' value='11' />	<label for='NonCP_11'>		<input type='checkbox' id='NonCP_11' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_11'>		<input type='checkbox' id='CP_11' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_11'>		<input type='checkbox' id='PCP_11' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_11'>		<input type='checkbox' id='LD_0_11' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_11'>		<input type='checkbox' id='LD_Less25_11' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_11'>		<input type='checkbox' id='LD_25to49_11' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_11'>		<input type='checkbox' id='LD_50to69_11' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_11'>		<input type='checkbox' id='LD_70to99_11' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_11'>		<input type='checkbox' id='LD_100_11' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_11'>		<input type='checkbox' id='NotObvious_11' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_11' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>OM1(12)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_12' name='Subject_No' value='12' />	<label for='NonCP_12'>		<input type='checkbox' id='NonCP_12' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_12'>		<input type='checkbox' id='CP_12' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_12'>		<input type='checkbox' id='PCP_12' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_12'>		<input type='checkbox' id='LD_0_12' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_12'>		<input type='checkbox' id='LD_Less25_12' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_12'>		<input type='checkbox' id='LD_25to49_12' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_12'>		<input type='checkbox' id='LD_50to69_12' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_12'>		<input type='checkbox' id='LD_70to99_12' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_12'>		<input type='checkbox' id='LD_100_12' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_12'>		<input type='checkbox' id='NotObvious_12' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_12' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>遠側端(13)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_13' name='Subject_No' value='13' />	<label for='NonCP_13'>		<input type='checkbox' id='NonCP_13' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_13'>		<input type='checkbox' id='CP_13' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_13'>		<input type='checkbox' id='PCP_13' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_13'>		<input type='checkbox' id='LD_0_13' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_13'>		<input type='checkbox' id='LD_Less25_13' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_13'>		<input type='checkbox' id='LD_25to49_13' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_13'>		<input type='checkbox' id='LD_50to69_13' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_13'>		<input type='checkbox' id='LD_70to99_13' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_13'>		<input type='checkbox' id='LD_100_13' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_13'>		<input type='checkbox' id='NotObvious_13' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_13' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>OM2(14)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_14' name='Subject_No' value='14' />	<label for='NonCP_14'>		<input type='checkbox' id='NonCP_14' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_14'>		<input type='checkbox' id='CP_14' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_14'>		<input type='checkbox' id='PCP_14' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_14'>		<input type='checkbox' id='LD_0_14' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_14'>		<input type='checkbox' id='LD_Less25_14' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_14'>		<input type='checkbox' id='LD_25to49_14' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_14'>		<input type='checkbox' id='LD_50to69_14' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_14'>		<input type='checkbox' id='LD_70to99_14' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_14'>		<input type='checkbox' id='LD_100_14' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_14'>		<input type='checkbox' id='NotObvious_14' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_14' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>PDA(15)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_15' name='Subject_No' value='15' />	<label for='NonCP_15'>		<input type='checkbox' id='NonCP_15' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_15'>		<input type='checkbox' id='CP_15' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_15'>		<input type='checkbox' id='PCP_15' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_15'>		<input type='checkbox' id='LD_0_15' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_15'>		<input type='checkbox' id='LD_Less25_15' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_15'>		<input type='checkbox' id='LD_25to49_15' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_15'>		<input type='checkbox' id='LD_50to69_15' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_15'>		<input type='checkbox' id='LD_70to99_15' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_15'>		<input type='checkbox' id='LD_100_15' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_15'>		<input type='checkbox' id='NotObvious_15' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_15' class='Remark' contenteditable='true'></div></td>
	    </tr>
	    <tr>
		    <td>L-PLB(18)</td>
		    <td class='AlignCenter'><input type='hidden' id='Subject_No_18' name='Subject_No' value='18' />	<label for='NonCP_18'>		<input type='checkbox' id='NonCP_18' name='NonCP' />	</label></td><td class='AlignCenter'>	<label for='CP_18'>		<input type='checkbox' id='CP_18' name='CP' />	</label></td><td class='AlignCenter'>	<label for='PCP_18'>		<input type='checkbox' id='PCP_18' name='PCP' />	</label></td><td class='AlignCenter'>	<label for='LD_0_18'>		<input type='checkbox' id='LD_0_18' name='LD_0' />	</label></td><td class='AlignCenter'>	<label for='LD_Less25_18'>		<input type='checkbox' id='LD_Less25_18' name='LD_Less25' />	</label></td><td class='AlignCenter'>	<label for='LD_25to49_18'>		<input type='checkbox' id='LD_25to49_18' name='LD_25to49' />	</label></td><td class='AlignCenter'>	<label for='LD_50to69_18'>		<input type='checkbox' id='LD_50to69_18' name='LD_50to69' />	</label></td><td class='AlignCenter'>	<label for='LD_70to99_18'>		<input type='checkbox' id='LD_70to99_18' name='LD_70to99' />	</label></td><td class='AlignCenter'>	<label for='LD_100_18'>		<input type='checkbox' id='LD_100_18' name='LD_100' />	</label></td><td class='AlignCenter'>	<label for='NotObvious_18'>		<input type='checkbox' id='NotObvious_18' name='NotObvious' />	</label></td><td class='AlignCenter'>		<div  id='Remark_18' class='Remark' contenteditable='true'></div></td>
	    </tr>
        <tr>
            <td>&nbsp;</td>
            <td>&nbsp;</td>
            <td>非鈣化<br>(non-  calcified plaque)</td>
            <td>鈣化<br>(calcified plaque)</td>
            <td>複合性鈣化<br>(partially calcified plaque)</td>
            <td rowspan="2">管腔直徑正常無狹窄</td>
            <td rowspan="2">管腔直徑狹窄&lt;25%</td>
            <td rowspan="2">管腔直徑狹窄25-49%</td>
            <td rowspan="2">管腔直徑狹窄50-69%</td>
            <td rowspan="2">管腔直徑狹窄70-99%</td>
            <td rowspan="2">管腔直徑完全阻塞</td>
            <td rowspan="2">此血管口徑細小或不明顯</td>
            <td rowspan="2">備註</td>
        </tr>
        <tr>
            <td>&nbsp;</td>
            <td>&nbsp;</td>
            <td colspan="3">斑塊</td>
        </tr>
    </table>
    </div>
    <div class="label-success PhotoListTitle">附加圖片</div>
    <div id="Attachment_Photo">
        <ul id="PreviewPhotoList" class="PhotoList">

        </ul>
    </div>
    
    <div id="Attachment_Photo_List">
            <ul class="TempPhotoList">

        </ul>
    </div>
</div>
<!-- Button trigger modal -->


<!-- Modal -->

<input type="hidden" id="ACCESSNO" name="ACCESSNO" value="341606165 " />
<input type="hidden" id="CNO" name="CNO" value="11490487" />
<input type="hidden" id="MODIFIED_STAFF" name="MODIFIED_STAFF" value=" " />
<input type="hidden" id="CHECK_PROJECT" name="CHECK_PROJECT" value="CACSCT" />

<div id="loding" style="z-index: 999;display:block;position: absolute;top: 0;left: 0;width: 100%;height: 100%;background-color: #ccc;filter:alpha(opacity=90);-moz-opacity:0.9;opacity: 0.9;"><div class="progress" style="position: absolute;top: 15%;left: 33%;width: 33%;"><div class="progress-bar progress-bar-striped active" role="progressbar" aria-valuenow="45" aria-valuemin="0" aria-valuemax="100" style="width: 100%;">Please Wait...</div></div></div>
<script src="/Scripts/bootstrap.min.js"></script>
<script src="/Scripts/textWidth.js"></script><!--加入可測量文字寬度的Function-->
<script src="/Scripts/jquery.dragsort-0.5.2.min.js"></script><!--加入拖移排序Library-->
<script src="/Scripts/GetGuid.js"></script><!--加入可產生GUID的Function-->
<script src="/Scripts/MainView.js"></script><!--載入罐頭訊息/LodingCover-->
<script>
    $('.collapse').collapse();//摺疊手風琴效果
    $(window).load(function () {
        Typesetting();
        Get_ListA_SubjectStrHide();//載入罐頭訊息
        //DefaultChecked();//勾選預設的checkbox
        if ($("#tempList p").length > 0) {
            $("#tempList p").each(function () {
                $("#ArteriesAnalysisAdvice").append("<li style='list-style-type: circle;' class='" + $(this).attr('class') + "'>" + $(this).text() + "</li>");
                if ($(this).attr('class') == "Abnormal") {
                    $("#PreviewAbnormalAAA").append("<li style='list-style-type: circle;' class='" + $(this).attr('class') + "'>" + $(this).text() + "</li>");
                }
                $(this).remove();
            });
        }
        CreateArteries();
    });
    $(document).ready(function () {
        $("#loding").hide();
        loadcss();
        Typesetting();
        RidTextboxBorder();
        $('[data-toggle="tooltip"]').tooltip();//滑鼠移入顯示提示訊息-bootstrap3.3.0
        /*選圖功能s*/
        $(".TempPhotoList li").click(function () {//顯示加入圖片按鈕
            $("#" + $(this).attr("id") + "_select").show();
        });
        $(".TempPhotoList li").mouseleave(function () {//隱藏加入圖片按鈕
            $(".PhotoSelect").hide();
        });
        $(".TempPhotoList .PhotoSelect div").click(function () {//加入圖片
            var liObj = $(this).parent().parent();
            var TagID = $(this).attr("data-tagid");
            toAttachmentPhoto(liObj, TagID);
        });
        /*選圖功能e*/
        $("#Add_Photo").click(function () {
            var data_id = $(this).attr("data-id");
            if ($("#" + data_id + "_IMG").length > 0) {
                $("#" + data_id + "_IMG").remove();
            }

            var ImgSrc = $('input:radio[name=TempPhotoRadio]:checked').val();
            $("#" + data_id).append("<img id='" + data_id + "_IMG' src='" + ImgSrc + "'/>");
            $('#myModal').modal('hide');
        });
        /*TypeA開啟關閉功能s*/
        $("#OpenEditor").click(function () {
            $("#OpenEditor").hide();
            $("#OpenEditorIng").show();
            if ($("#accordion").length > 0) {
                $("#accordion").show();
                $("#OpenEditorIng").hide();
                $("#CloseEditor").show();
            } else {
                Get_ListA_SubjectStr();
            }
        });
        $("#CloseEditor").click(function () {
            $("#accordion").hide();
            $("#CloseEditor").hide();
            $("#OpenEditor").show();
        });
        /*TypeA開啟關閉功能e*/
        $("#PreviewUl").dragsort();//加入拖移排序效果

        //動脈概化分析組字串送到preview_S
        $(".AlignCenter input").change(function () {
            CreateArteries();
        });
        $(".Remark").blur(function () {
            CreateArteries();
        });
        //動脈概化分析組字串送到preview_E
    });
    
    function Typesetting() {//調整版面初始
        $('input:text').each(function () {
            var textwidth = $(this).textWidth();
            $(this).css('width', textwidth + 6 + 'px');
        });
    }
    function RidTextboxBorder() {
        $("input:text[content_type='text']").each(function () {
            $(this).css("border-width", "0px");
        });
    }
    function CheckboxsDisabled() {
        $('input:checkbox').each(function () {
            $(this).attr('disabled', 'disabled');
        });
    }





    function InstantTypesetting(Obj) {//調整版面預覽隨打隨調
        var textwidth = Obj.textWidth();
        Obj.css('width', textwidth + 'px');
        if (Obj.parent().attr("class").indexOf("Abnormal")) {//與總結文字同步
            $("#PreviewAbnormal #" + Obj.parent().attr("id")).find("input").val(Obj.val());
            $("#PreviewAbnormal #" + Obj.parent().attr("id")).find("input").css('width', textwidth + 'px');
        }
    }
    function savedata() {
        if (parseInt(Check_dominant()) > 0) {
            LoadingCover();
            Store_TypeA();
        } else {
            alert("請先勾選冠狀動脈顯要性!");
            var scrollPx = parseInt($(document).outerHeight(true))*0.42;
            $("html,body").animate({ scrollTop: scrollPx+"px" });//網頁滑到"冠狀動脈顯要性"的位置
        }
    }
    function Check_dominant() {
        var CountChecked = $(".dominant:checked").length;
        return CountChecked;
    }
    function htmlEncode(value) {
        return $('<div/>').text(value).html();
    }
    function Store_TypeA() {
        $("#PreviewUl li").each(function () {
            $(this).find("input").attr("value", $(this).find("input").val());
        });
        var StoredHtmlStr = htmlEncode($("#PreviewUl").html());
        $.ajax({
            url: 'SaveTypA',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                CNO: $("#CNO").val(),
                CHECK_PROJECT: "CACSCT",
                MODIFIED_STAFF: $("#MODIFIED_STAFF").val(),
                HTML_STR: StoredHtmlStr
            },
            success: function (data) {
                if (data == "True") {
                    Store_Advice();
                } else {
                    alert("Save failed");
                    $("#loding").fadeOut("slow");
                }
            }
        });
    }
    function Store_Advice() {
        var JsonObjList = [];
        $("#Advice input:checked").each(function () {
            var JsonObj = new Object();
            JsonObj["SUBJECT_ID"] = $(this).attr("id");
            JsonObj["SUBJECT_CONTENT"] = $(this).val();
            JsonObjList.push(JsonObj);
        });

        var JsonObj = new Object();
        JsonObj["SUBJECT_ID"] = "textarea";
        JsonObj["SUBJECT_CONTENT"] = $("#Advice textarea").val();
        JsonObjList.push(JsonObj);

        var JsonObj = new Object();
        JsonObj["SUBJECT_ID"] = "NormalResult";
        JsonObj["SUBJECT_CONTENT"] = $("#NormalResult").prop("checked");
        JsonObjList.push(JsonObj);

        var JsonStr = JSON.stringify(JsonObjList);
        $.ajax({
            url: 'SaveAdvice',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                CNO: $("#CNO").val(),
                CHECK_PROJECT: "CACSCT",
                MODIFIED_STAFF: $("#MODIFIED_STAFF").val(),
                JsonStr: JsonStr
            },
            success: function (data) {
                SaveAdvicePhoto();
            }
        });
    }
    function UploadFile(data_id) {
        var formData = new FormData($("#" + data_id)[0]);
        $.ajax({
            url: "UploadPhoto",
            type: 'POST',
            data: formData,
            async: false,
            success: function (data) {
                //alert(data);
            },
            cache: false,
            contentType: false,
            processData: false
        });
    }
    function SaveAdvicePhoto() {
        var JsonObjList = [];
        $("#AdvicePhotoList li").each(function () {
            var JsonObj = new Object();
            JsonObj["PhotoFileName"] = $(this).find("img").attr("data-filename");
            JsonObjList.push(JsonObj);
        });
        $.ajax({
            url: 'SaveAttachmentPhoto',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                CNO: $("#CNO").val(),
                CHECK_PROJECT: "CACSCT",
                MODIFIED_STAFF: $("#MODIFIED_STAFF").val(),
                PhotoFileNameJson: JSON.stringify(JsonObjList),
                PhotoDisplayPosition: "Advice"
            },
            success: function (data) {
                //alert(data);
                if (data == "True") {
                    Store_FormCACS();
                } else {
                    alert("Save failed");
                    $("#loding").fadeOut("slow");
                }
            }
        });
    }
    function Store_FormCACS() {
        $.ajax({
            url: 'SaveFormCACS',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                CNO: $("#CNO").val(),
                CHECK_PROJECT: "CACSCT",
                LMA_Score: $("#LMA_Score").text(),
                LMA_Explain: $("#LMA_Explain").text(),
                LAD_Score: $("#LAD_Score").text(),
                LAD_Explain: $("#LAD_Explain").text(),
                LCX_Score: $("#LCX_Score").text(),
                LCX_Explain: $("#LCX_Explain").text(),
                RCA_Score: $("#RCA_Score").text(),
                RCA_Explain: $("#RCA_Explain").text(),
                Total_Score: $("#Total_Score").text(),
                Total_Explain: $("#Total_Explain").text(),
                Calcium_Score: $("#Calcium_Score").text(),
                MODIFIED_STAFF: $("#MODIFIED_STAFF").val()
            },
            success: function (data) {
                //alert(data);
                Store_FormCT();
                //if (data == "True") {
                //    $("#loding").fadeOut("slow");
                //    window.location.reload();
                //}
            }
        });
    }
    function AdviceReadURL(input, data_id) {
        if ($("#Pre_PhotoForm").length > 0) {
            $("#Pre_PhotoForm").remove();
        }
        $("#PhotoField").append('<img id="Pre_PhotoForm" src="#" alt="Photo" />');
        if (input.files && input.files[0]) {
            var reader = new FileReader();
            reader.onload = function (e) {
                $('#Pre_PhotoForm').attr('src', e.target.result);
            }
            reader.readAsDataURL(input.files[0]);
        }
        UploadFile(data_id);
    }
    function RemovePhoto(Obj_Id) {
        $("#" + Obj_Id).html($("#" + Obj_Id).html());
        $("#Pre_" + Obj_Id).remove();
    }
    function Store_FormCT() {
        var formData = new FormData($("#FORM_CT")[0]);
        $.ajax({
            url: "SaveFormCT",
            type: 'POST',
            data: formData,
            async: false,
            success: function (data) {
                //alert(data);
                if (data == "True") {
                    SaveArteriesForm();
                } else {
                    alert("Save failed");
                    $("#loding").fadeOut("slow");
                }
            },
            cache: false,
            contentType: false,
            processData: false
        });
    }
    function SaveArteriesForm()
    {
        var JsonObjList = [];
        $("#ArteriesForm table tr").each(function () {
            if ($(this).find("input").length > 0) {     
                var Subject_No=$(this).find("input[name='Subject_No']").val();
                var JsonObj = new Object();
                JsonObj["Subject_No"] = $(this).find("input[name='Subject_No']").val();
                JsonObj["NonCP"] = $(this).find("input[name='NonCP']").prop('checked');
                JsonObj["CP"] = $(this).find("input[name='CP']").prop('checked');
                JsonObj["PCP"] = $(this).find("input[name='PCP']").prop('checked');
                JsonObj["LD_0"] = $(this).find("input[name='LD_0']").prop('checked');
                JsonObj["LD_Less25"] = $(this).find("input[name='LD_Less25']").prop('checked');
                JsonObj["LD_25to49"] = $(this).find("input[name='LD_25to49']").prop('checked');
                JsonObj["LD_50to69"] = $(this).find("input[name='LD_50to69']").prop('checked');
                JsonObj["LD_70to99"] = $(this).find("input[name='LD_70to99']").prop('checked');
                JsonObj["LD_100"] = $(this).find("input[name='LD_100']").prop('checked');
                JsonObj["NotObvious"] = $(this).find("input[name='NotObvious']").prop('checked');
                JsonObj["Remark"] = $(this).find("#Remark_" + Subject_No).text();
                JsonObjList.push(JsonObj);
            }
        });
        $.ajax({
            url: 'SaveFormArteries',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                CNO: $("#CNO").val(),
                CHECK_PROJECT: "CACSCT",
                MODIFIED_STAFF: $("#MODIFIED_STAFF").val(),
                ArteriesFormJson: JSON.stringify(JsonObjList)
            },
            success: function (data) {
                if (data == "True") {
                    StoreAttachmentPhoto()
                    //$("#loding").fadeOut("slow");
                    //window.location.reload();
                } else {
                    alert("Save failed");
                    $("#loding").fadeOut("slow");
                }
            }
        });
    }
    function StoreAttachmentPhoto() {
        var JsonObjList = [];
        $("#PreviewPhotoList li").each(function () {
            var JsonObj = new Object();
            JsonObj["PhotoFileName"] = $(this).find("img").attr("data-filename");
            JsonObjList.push(JsonObj);
        });
        $.ajax({
            url: 'SaveAttachmentPhoto',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                CNO: $("#CNO").val(),
                CHECK_PROJECT: "CACSCT",
                MODIFIED_STAFF: $("#MODIFIED_STAFF").val(),
                PhotoFileNameJson: JSON.stringify(JsonObjList),
                PhotoDisplayPosition: "Attachment"
            },
            success: function (data) {
                //alert(data);
                if (data == "True") {
                    $("#loding").fadeOut("slow");
                    //window.location.reload();
                } else {
                    alert("Save failed");
                    $("#loding").fadeOut("slow");
                }
            }
        });
    }
    function loadcss() {//載入樣式
        $("<link>").attr({
            rel: "stylesheet",
            type: "text/css",
            href: "/Content/EditCACSCT.css"
        }).appendTo("head");
    }
    function toAttachmentPhoto(Obj, TagID) {
        var PreviewLi_Id = GetGuid();
        var imgSrc = Obj.find("img").attr("src");
        var imgAlt = Obj.find("img").attr("alt");
        var FileName = Obj.find("img").attr("data-filename");
        var imgClass = Obj.find("img").attr("class");
        var imgHtml = "<img src='" + imgSrc + "' alt='" + imgAlt + "' data-filename='" + FileName + "' class='" + imgClass + "'/>";
        var imgObj = "<li id='" + PreviewLi_Id + "'>" + imgHtml + "<button type='button' class='close' onclick='RemoveItem(\"" + PreviewLi_Id + "\");'><span aria-hidden='true'>&times;</span><span class='sr-only'>Close</span></button></li>";
        $.ajax({
            url: 'CopeAttachmentPhoto',
            type: 'post',
            data: {
                ACCESSNO: $("#ACCESSNO").val(),
                FileName: FileName
            },
            success: function (data) {
                $("#" + TagID).append(imgObj);
            }
        });
    }
    function toPDF() {
        $(window.location).attr('href', "/PDF/DownloadPdf");
    }
    function previewPDF() {
        $(window.location).attr('href', "/PDF/PDFPreview");
    }
    function toHome() {
        $(window.location).attr('href', "/Main/DoctorEditList?ACCESSNO=341606165 ");
        //$(window.location).attr('href', "/Main/DoctorEditList?ACCESSNO=MzQxNjA2MTY1IA==");
    }
    function Get_ListA_SubjectStr() {
        $.ajax({
            url: '/Main/CreateListA',
            type: 'post',
            success: function (result) {
                $("#EditArea").append(result);
                $('.collapse').collapse();//摺疊手風琴效果
                Typesetting();
                RidTextboxBorder();
                $("#OpenEditorIng").hide();
                $("#CloseEditor").show();
            }
        });
    }

    function DefaultChecked() {
        $(".ArteriesTable tr").each(function () {
            if ($(this).find("input[type=checkbox]:checked").length == 0) {
                $(this).find("input[type=checkbox]:eq(3)").prop("checked", true);
            }
        });
        CreateArteries();
    }
</script>

    
</body>
</html>
