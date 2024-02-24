# SQL-Data-Analysis
-- first we create schema or database --
create schema cars;     
use cars;   
-- upload carcdekho.csv file then perform sql query to analysis data --
select * from cars.car_dekho;
-- Read car data --
select * from car_dekho;
-- Total Cars : To get a count of total records --
select count(*) from car_dekho;
-- The manager asked the employees how many cars is avalible in 2023 --
select count(*) from car_dekho where year=2023;
-- The manager asked the employees how many cars is avalible in 2020,2021,2022 --
select count(*) from car_dekho where year=2020; #74
select count(*) from car_dekho where year=2021; #7
select count(*) from car_dekho where year=2022; #7
-- group by --
select count(*) from car_dekho where year in (2020,2021,2022) group by year;
-- Client asked me to print the total of all cars by years , I don't see allthe details --
select year , count(*) from car_dekho group by year;
-- Client asked to car dealer agent how many diesel cars will there be in 2020?  --
select count(*) from car_dekho where year = 2020 and fuel = 'DIESEL';
-- Client requested a car dealer agent how many petrol cars will there be in 2020?  --
select count(*) from car_dekho where year = 2020 and fuel = 'PETROL'; # 51
-- The manager told the employee to give a print of all fuel cars (petrol, diesel and CNG) come from all year --
select year,count(*) from car_dekho where fuel = 'PETROL' group by year;
select year,count(*) from car_dekho where fuel = 'DIESEL' group by year;
select year,count(*) from car_dekho where fuel = 'CNG' group by year;
-- manager said there were mare then 100 cars in a given, which year had more than 100 cars? --
select year,count(*) from car_dekho group by year having count(*) > 100;
select year,count(*) from car_dekho group by year having count(*) < 50;
-- The manager said to the employee All the cars count details between 2015 and 2023 , we need complete list -- 
select year , count(*) from car_dekho where year in (2015,2023) group by year;
