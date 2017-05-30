# hivewc
create table wc(line String);
load data local inpath '/home/acadgild/Desktop/new file' into table wc;
create view wc_view as select explode(split(line,',')) as words from wc;
select words,count(words) from wc_view group by words;
