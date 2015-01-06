SELECT     sn_no, COUNT(*) AS dupes  
FROM     SN_TRANS 
where SN_NO in(select SN_NO from SN where ORD_NO = '5490562')
and PROC_CD = 'REGISTER'
GROUP BY sn_no  
HAVING (COUNT(*) > 1)
