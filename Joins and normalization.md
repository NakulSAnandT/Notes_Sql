
Joins and Normalization
 The whole purpose of join is to allow us to pull data from one or more than one table at a time

INNER JOIN : Returns matching row from both the tables (intersection) 
	The rows should be available in both the tables 
	Syntax : ![[InnerJoin.png]]
	i want to bring customer rows into orders here
	(condition/matched rows rand rabililum illadhine return aakum)
LEFT JOIN : Returns the whole Left table and returns only matching rows of Right table 
	![[Left Join.png]]
		![[Left  join2.png]]
RIGHT JOIN : Returns the whole right left table and returns only matching rows of Left
FULL OUTER JOIN : Returns all tables even with the unmatched rows
CROSS JOIN : Returns the cartesian
	(a,b,c)(1,2,3) = (a,1)(a,2)(a,3)(b,1) etc..