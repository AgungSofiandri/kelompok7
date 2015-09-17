# kelompok7
<?
	include "koneksi.php";
	$qry = mysql_query("select * from tbl_barang order by kode_barang");
?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Sistem Informasi Penjualan - By : Wardoyo</title>
<link href="file:///C|/xampp/htdocs/kelompok7/desain.css" rel="stylesheet" type="text/css" />
<script type="text/javascript">
function MM_jumpMenu(targ,selObj,restore){ //v3.0
  eval(targ+".location='input_penjualan.php?kode"+selObj.options[selObj.selectedIndex].value+"'");
  if (restore) selObj.selectedIndex=0;
}
</script>
<style type="text/css">
<!--
body {
	background-color: #CCCCCC;
}
-->
</style></head>

<body>
<table width="100%" border="0" cellspacing="0" cellpadding="0">
  <tr>
    <td colspan="3">&nbsp;</td>
  </tr>
  <tr>
    <td width="20%" height="500" valign="top" class="garis_utama"><table width="100%" border="0" cellspacing="0" cellpadding="3">
      <tr>
        <td align="center" class="menu_utama">&nbsp;</td>
      </tr>
      <tr>
        <td align="center" class="isi_menu">&nbsp;</td>
      </tr>
      <tr>
        <td align="center" class="isi_menu">&nbsp;</td>
      </tr>
      <tr>
        <td align="center" class="isi_menu">&nbsp;</td>
      </tr>
      <tr>
        <td align="center" class="isi_menu">&nbsp;</td>
      </tr>
    </table></td>
    <td width="60%" valign="top"><table width="100%" border="0" cellspacing="0" cellpadding="3">
      <tr>
        <td align="center" class="menu_utama">&nbsp;</td>
      </tr>
      <tr>
        <td><form id="form1" name="form1" method="post" action="file:///C|/xampp/htdocs/kelompok7/simpan_barang.php">
          <table width="100%" border="1" cellspacing="0" cellpadding="3">
            <tr>
              <td width="40%">&nbsp;</td>
              <td width="4%">:</td>
              <td width="60%"><select name="kode" onchange="MM_jumpMenu('parent',this,0)" id="kode">
                <option value="file:///C|/xampp/htdocs/kelompok7/0" selected="selected"></option>
                <?								
								while($dt = mysql_fetch_array($qry))
								{
									$kodenya = $dt["kode"];
									$namanya = $dt["nama"];
									$harga = $dt["harga"];
							?>
                <option value="<? echo $nonya ?>" <? if($_REQUEST["kode"] == $kodenya) echo "selected"; ?>><? echo $kodenya; ?></option>
                <?
								}
							?>
              </select></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>:</td>
              <td><input type="text" name="nama" id="nama" value="" /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>:</td>
              <td><input type="text" name="harga" id="harga" value="" /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>:</td>
              <td><input type="text" name="nofaktur" id="nofaktur" /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>:</td>
              <td><select name="cbo_tgl" id="cbo-3">
                <option value="0" selected="selected"></option>
                <?
				for($x=1;$x<=31;$x++)
				{
			?>
                <option value="<? echo $x ?>" <? if($cbo_tgl == $x) echo "selected"; ?>><? echo $x; ?></option>
                <?
				}
			?>
              </select> 
                - 
                <select name="cbo_bln" id="cbo-2">
                  <option value="0" selected="selected"></option>
                  <option value="01" <? if($cbo_bln == "01") echo "selected"; ?>>Januari</option>
                  <option value="02" <? if($cbo_bln == "02") echo "selected"; ?>>Februari</option>
                  <option value="03" <? if($cbo_bln == "03") echo "selected"; ?>>Maret</option>
                  <option value="04" <? if($cbo_bln == "04") echo "selected"; ?>>April</option>
                  <option value="05" <? if($cbo_bln == "05") echo "selected"; ?>>Mei</option>
                  <option value="06" <? if($cbo_bln == "06") echo "selected"; ?>>Juni</option>
                  <option value="07" <? if($cbo_bln == "07") echo "selected"; ?>>Juli</option>
                  <option value="08" <? if($cbo_bln == "08") echo "selected"; ?>>Agustus</option>
                  <option value="09" <? if($cbo_bln == "09") echo "selected"; ?>>September</option>
                  <option value="10" <? if($cbo_bln == "10") echo "selected"; ?>>Oktober</option>
                  <option value="11" <? if($cbo_bln == "11") echo "selected"; ?>>November</option>
                  <option value="12" <? if($cbo_bln == "12") echo "selected"; ?>>Desember</option>
                </select> 
                - 
                <select name="cbo_thn" id="select">
                  <option value="0" selected="selected"></option>
                  <?
				for($x=date("Y");$x>=date("Y")-100;$x--)
				{
			?>
                  <option value="<? echo $x ?>" <? if($cbo_thn == $x) echo "selected"; ?>><? echo $x; ?></option>
                  <?
				}
			?>
                </select></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>:</td>
              <td><input type="text" name="qty" id="qty" /></td>
            </tr>
            <tr>
              <td>&nbsp;</td>
              <td>:</td>
              <td><input type="text" name="total" id="total" /></td>
            </tr>
            <tr>
              <td colspan="3" align="center"><input type="submit" name="proses" id="proses" value="Simpan" /> 
                <input type="reset" name="button2" id="button2" value="Reset" /></td>
              </tr>
          </table>
        </form></td>
      </tr>
    </table></td>
    <td width="20%" valign="top" class="garis_utama"><table width="100%" border="0" cellspacing="0" cellpadding="3">
      <tr>
        <td class="menu_utama">&nbsp;</td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.google.com" target="_blank"></a></td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.yahoo.com" target="_blank"></a></td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.facebook.com" target="_blank"></a></td>
      </tr>
      <tr>
        <td class="isi_menu"><a href="http://www.twitter.com" target="_blank"></a></td>
      </tr>
    </table></td>
  </tr>
  <tr>
    <td colspan="3" align="center" class="garis_footer">
      Copy Right (C) 2015 - By : Kelompok7
    </td>
  </tr>
</table>
</body>
</html>
