# Python_XML_CSV_Solution
Solution to a problem to fetch url of a zip out of a xml on a url, download and unzip, get the xml file inside the zip  and convert it to csv upload to aws s3 bucket



download_first_xml(link)
Downloads XML file from a provided link into feed.xml
https://registers.esma.europa.eu/solr/esma_registers_firds_files/select?q=*&fq=publication_date:%5B2020-01-08T00:00:00Z+TO+2020-01-08T23:59:59Z%5D&wt=xml&indent=true&start=0&rows=100

read_first_xml_provide_url(path)
Read the xml and find the zip file url out of it (parse through to the first download link whose file_type is DLTINS) 

download_zip(download_url)
Download the zip file onto xml_inside.zip file

unzip_getxml()
Unzip the contents of xml_inside.zip (xml file/files) onto targetdir folder

upload_to_aws(local_file, bucket, s3_file)
Upload the given local_file onto bucket name bucket with s3_file in s3 aws using ACCESS_KEY and SECRET_KEY

xml_tocsv_uploadaws(zippath='targetdir')

    Convert the contents of the xml into a CSV with the following header:

    FinInstrmGnlAttrbts.Id
    FinInstrmGnlAttrbts.FullNm
    FinInstrmGnlAttrbts.ClssfctnTp
    FinInstrmGnlAttrbts.CmmdtyDerivInd
    FinInstrmGnlAttrbts.NtnlCcy
    Issr
CSV file name as xml_filename.xml.csv

and Upload this file to aws s3 bucket
