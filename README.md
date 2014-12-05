



add jar /home/hadoop/hive-customer-udf-1.0-SNAPSHOT.jar;

CREATE TEMPORARY FUNCTION decode AS 'com.sponge.srd.hive.udf.UDFDecode';
CREATE TEMPORARY FUNCTION encode AS 'com.sponge.srd.hive.udf.UDFEncode';


select encode('facebook') from tmp;
select encode('facebook','fkey','skey','tkey') from tmp;

select decode('1CC7376126B8AE1DE343E4C20EAE9ADA') from tmp;
select decode('5BB6A40B0CEA149B0A1645E74C7E460C','fkey','skey','tkey') from tmp;