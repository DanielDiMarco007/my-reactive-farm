En esta actividad se agregó un nuevo filtro por edad mínima a la aplicación. 

Estado del nuevo filtro; Se creó un estado adicional para almacenar la edad mínima ingresada por el usuario:const [minAge, setMinAge] = useState(0); Este estado se inicializa en 0 para que, por defecto, no se excluya ningún animal.

Lógica de filtrado

Se ajustó la derivación de la lista filtrada (filteredAnimals) agregando una condición que verifica si cada animal cumple con la edad mínima:const byMinAge = a.age >= minAge;

Esta condición se combina con los filtros existentes (typeFilter, statusFilter y query), de modo que un animal solo se muestra si cumple todos los criterios:

return byType && byStatus && byQuery && byMinAge;
