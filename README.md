# customer_rating_system
h2: select sum(transaction_amt) from transaction where transaction_type="INN" and transaction_amt>1000 groupby extract(month) from date;
m4 : select count(*) from transaction where day=(query.day) ;
h4: select count(*) from transaction where day=(query.day) 


 
h4: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST([transfer_date] AS DATE) ,
         account_key ,
         COUNT(account_key) AS counter
FROM     transaction where counter>20
GROUP BY CAST([transfer_date] AS DATE) ,
         account_key;);
		 
		 
m4: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST([transfer_date] AS DATE) ,
         account_key ,
         COUNT(account_key) AS counter
FROM     transaction where counter>10 and counter<20
GROUP BY CAST([transfer_date] AS DATE) ,
         account_key;);
		 
l4:(select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST([transfer_date] AS DATE) ,
         account_key ,
         COUNT(account_key) AS counter
FROM     transaction where counter<10
GROUP BY CAST([transfer_date] AS DATE) ,
         account_key;);



h4: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST([transfer_date] AS DATE) ,
         account_key ,
         COUNT(account_key) AS counter
FROM     transaction where counter>20
GROUP BY CAST([transfer_date] AS DATE) ,
         account_key;);
		 
		 
m4: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST([transfer_date] AS DATE) ,
         account_key ,
         COUNT(account_key) AS counter
FROM     transaction where counter>10 and counter<20
GROUP BY CAST([transfer_date] AS DATE) ,
         account_key;);
		 
l4:(select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST([transfer_date] AS DATE) ,
         account_key ,
         COUNT(account_key) AS counter
FROM     transaction where counter<10
GROUP BY CAST([transfer_date] AS DATE) ,
         account_key;);



h3: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST(EXTRACT MONTH FROM [transfer_date] AS MONTH) ,
         account_key ,
         COUNT(transaction_amt) AS counter
FROM     transaction where counter>800 and transaction_type="OUT"
GROUP BY CAST([transfer_date] AS MONTH) ,
         account_key;);
		 
M3: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST(EXTRACT MONTH FROM [transfer_date] AS MONTH) ,
         account_key ,
         sum(transaction_amt) AS counter
FROM     transaction where counter>500 and counter<800 and transaction_type="OUT"
GROUP BY CAST([transfer_date] AS MONTH) ,
         account_key;);

l3: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST(EXTRACT MONTH FROM [transfer_date] AS MONTH) ,
         account_key ,
         COUNT(transaction_amt) AS counter
FROM     transaction where counter<500 and transaction_type="OUT"
GROUP BY CAST([transfer_date] AS MONTH) ,
         account_key;);



h2: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST(EXTRACT MONTH FROM [transfer_date] AS MONTH) ,
         account_key ,
         COUNT(transaction_amt) AS counter
FROM     transaction where counter>1000 and transaction_type="INN"
GROUP BY CAST([transfer_date] AS MONTH) ,
         account_key;);
		 
M2: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST(EXTRACT MONTH FROM [transfer_date] AS MONTH) ,
         account_key ,
         sum(transaction_amt) AS counter
FROM     transaction where counter>600 and counter<1000 and transaction_type="INN"
GROUP BY CAST([transfer_date] AS MONTH) ,
         account_key;);

l2: (select count(*) from transaction t, account_info a where t.account_key==a.account_key and a.customer_key==query.customer_key  in  (SELECT  CAST(EXTRACT MONTH FROM [transfer_date] AS MONTH) ,
         account_key ,
         COUNT(transaction_amt) AS counter
FROM     transaction where counter<600 and transaction_type="INN"
GROUP BY CAST([transfer_date] AS MONTH) ,
         account_key;);
