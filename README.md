# procedimiento-2
procedimiento que consulta un cliente su consumo de luz el total y muestra los empleados que fueron a tomar las medidas del medidor
create procedure empleados3
@cedula_empleado char(12)
as

select e.nombre_empleado,cl.nombres,c.numero_medidorpk,c.consumo_luz,c.total_l from ConsumodeElectrico c
	inner join medidor  m on c.numero_medidorpk=m.numero_medidor
	inner join empleados e on e.cedula_empleado=c.cedula_empleadopk inner join clientes cl on  cl.cedula_cliente= c.cedula_clientepk
select sum(total_l) as total from ConsumodeElectrico 
	inner join clientes s on cedula_cliente=cedula_clientepk
where nombres ='Mauro Enrique'

go
exec empleados3 '123444'
