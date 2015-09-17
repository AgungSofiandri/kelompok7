# kelompok7
<?
	//koneksi ke database
	include "koneksi.php";
	//ambil nilai dari masing-masing komponen form
	$kode = $_REQUEST["kode"];
	$nama = $_REQUEST["nama"];
	$satuan = $_REQUEST["satuan"];
	$harga = $_REQUEST["harga"];
	$stock = $_REQUEST["stock"];
	//kondisi jika data belum lengkap
	if ($kode == "" || $nama == "" || $harga == "" || $stock == "")
	{
		?>
        <script type="text/javascript">
		alert ("Lengkapi Data")
		document.location.href="input_barang.php";
		</script>
        <?
	}
	else 
	{
		//cek apakah kode sudah ada atau belum
		$cek_data = "select * from tbl_barang where kode_barang = '$kode'";
		//eksekusi perintah SQL
		$hasil = mysql_query($cek_data);
		//jika kode barang sudah ada
		if (mysql_num_rows($hasil) > 0)
		{
			?>
        	<script type="text/javascript">
			alert ("Kode Barang Sudah Ada !!")
			document.location.href="input_barang.php";
			</script>
       		<?
		}
		else
		{
			//proses simpan
			$simpan = "insert into tbl_barang values ('$kode','$nama','$satuan','$harga','$stock')";
			$hasil_simpan = mysql_query($simpan);
			?>
        	<script type="text/javascript">
			alert ("Data Berhasil Disimpan !!")
			document.location.href="input_barang.php";
			</script>
       		<?
		}
	}
?>
