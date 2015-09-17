# kelompok7
/*
SQLyog Enterprise - MySQL GUI v7.14 
MySQL - 5.0.27-community-nt-log : Database - db_eks1
*********************************************************************
*/


/*!40101 SET NAMES utf8 */;

/*!40101 SET SQL_MODE=''*/;

/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;

CREATE DATABASE /*!32312 IF NOT EXISTS*/`db_eks1` /*!40100 DEFAULT CHARACTER SET utf8 */;

USE `db_eks1`;

/*Table structure for table `tbl_barang` */

DROP TABLE IF EXISTS `tbl_barang`;

CREATE TABLE `tbl_barang` (
  `kode_barang` char(10) NOT NULL,
  `nama_barang` varchar(30) NOT NULL,
  `satuan` varchar(15) NOT NULL,
  `harga` decimal(10,0) NOT NULL default '0',
  `stock` int(11) NOT NULL default '0',
  PRIMARY KEY  (`kode_barang`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 CHECKSUM=1 DELAY_KEY_WRITE=1 ROW_FORMAT=DYNAMIC;

/*Data for the table `tbl_barang` */

insert  into `tbl_barang`(`kode_barang`,`nama_barang`,`satuan`,`harga`,`stock`) values ('B001','Kulkas 2 Pintu','Unit','2000000',20),('B002','LCD TV 21 Inc','Unit','3000000',10),('B003','Tape Recorder','Unit','1000000',15);

/*Table structure for table `tbl_penjualan` */

DROP TABLE IF EXISTS `tbl_penjualan`;

CREATE TABLE `tbl_penjualan` (
  `no_faktur` char(15) NOT NULL,
  `tgl_faktur` date NOT NULL,
  `kode_barang` char(10) NOT NULL,
  `qty` int(11) NOT NULL default '0',
  `total_harga` decimal(10,0) NOT NULL default '0',
  PRIMARY KEY  (`no_faktur`,`kode_barang`),
  KEY `relasi1` (`kode_barang`),
  CONSTRAINT `relasi1` FOREIGN KEY (`kode_barang`) REFERENCES `tbl_barang` (`kode_barang`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8 CHECKSUM=1 DELAY_KEY_WRITE=1 ROW_FORMAT=DYNAMIC;

/*Data for the table `tbl_penjualan` */

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
