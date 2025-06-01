clear all
set more off

////////////////////////////////////////////////////////////////////////////////
//																			                                      //
//		  	INSTITUTO DE INVESTIGACIONES SOCIO-ECONÓMICAS IISEC				          //
//																	                                          //
////////////////////////////////////////////////////////////////////////////////

**	PROYECTO:					INDICADORES DE DEMOGRAFÍA, SALUD SEXUAL Y REPRODUCTIVA
**  IDENTIFICADOR:				grap_demografía_salud_sexual_y_reproductiva.do
**	AUTOR:						ALEJANDRA ARLETH LAFUENTE LUIZAGA
**  FECHA DE CREACIÓN: 			06.06.2024
**	ÚLTIMO EN MODIFICAR: 		ARLETH LAFUENTE (aalafuentelui@gmail.com)
**	FECHA DE MODIFICACIÓN: 		16.10.2024

**************************************************************************
**************************************************************************

*	PROYECTO: 	INDICADORES DE DEMOGRAFÍA, SALUD SEXUAL Y REPRODUCTIVA

**************************************************************************
**************************************************************************
*	CONTENIDO:
/*
	1. Formato imágenes
	2. Indicadores
		6.1 Población Grupos Especiales
			6.1.1. Número de Mujeres en Edad Fértil (MEF)
				6.1.1.1. Nacional
				6.1.1.2. Departamental
			6.1.2. Proporción de Mujeres en Edad Fértil (MEF)
				6.1.2.1. Nacional
				6.1.2.2. Departamental
			6.1.3. Número de embarazos
				6.1.3.1. Nacional 
				6.1.3.2. Departamental
			6.1.4. Número de partos
				6.1.4.1. Nacional
				6.1.4.2. Departamental
			6.1.5. Número de abortos
				6.1.5.1. Nacional
				6.1.5.2. Departamental
			6.1.6. Proporción de partos y abortos sobre embarazos
				6.1.6.1. Nacional
				6.1.6.2. Departamental
			6.1.7. Número de nacimientos
				6.1.7.1. Nacional
				6.1.7.2. Departamental
			6.1.8. Número de Hijos Nacidos Vivos (HNV)
				6.1.8.1 Nacional
				6.1.8.2 Departamental
			6.1.9. Número de Hijos Nacidos Muertos (HNM)
				6.1.9.1 Nacional
				6.1.9.1 Departamental
			6.1.10. Proporción de HNV e HNM sobre nacimientos
				6.1.10.1. Nacional
				6.1.10.2. Departamental
		6.2. Salud Sexual y Reproductiva
			6.2.1. Tasa de Aborto General (TAG) 
				6.2.1.1. Nacional
				6.2.1.2. Departamental
			6.2.2. Tasa de Fecundidad General (TFG)
				6.2.2.1. Nacional
				6.2.2.2. Departamental
			6.2.3. Tasa de Mortalidad Fetal (TMF)
				6.2.3.1. Nacional
				6.2.3.2. Departamental
			6.2.4. Tasa Estimada de Embarazo (TEE)
				6.2.4.1. Nacional
				6.2.4.2. Departamental
		6.3. Demografía
			6.3.1. Tasa Bruta de Natalidad (TBN)
				6.3.1.1. Nacional
				6.3.1.2. Departamental
			6.3.2. Índice de Masculinidad (IM)
				6.3.2.1. Nacional
				6.3.2.2. Departamental
			6.3.3. Tasa de Crecimiento Poblacional (TCP)
				6.3.3.1. Nacional
				6.3.3.2. Departamental
			6.3.4. Distribución de la Población por Grupos Etarios (DPGE)
				6.3.4.1. Nacional
				6.3.4.2. Departamental
			6.3.5. Índice de Dependencia Potencial (IDP)
				6.3.5.1. Nacional
				6.3.5.2. Departamental
			6.3.6. Índice de Envejecimiento (IE)
				6.3.6.1. Nacional
				6.3.6.2. Departamental
			6.3.7. Índice de Dependencia Juvenil (IDJ)
				6.3.7.1. Nacional
				6.3.7.2. Departamental
			6.3.8. Índice de Dependencia Senil (IDS)
				6.3.8.1. Nacional
				6.3.8.2. Departamental
			6.3.9. Edad Mediana de la Población (EMDP)
				6.3.9.1. Nacional
				6.3.9.2. Departamental
			6.3.10. Edad Media de la Población (EMP)
				6.3.10.1. Nacional
				6.3.10.2. Departamental
			6.3.11. Índice de Reemplazamiento de la Población en Edad Activa (IRPEA)
				6.3.11.1. Nacional
				6.3.11.2. Departamental
			6.3.12. Índice de Estructura de la Población en Edad Activa (IEPEA)
				6.3.12.1. Nacional
				6.3.12.2. Departamental
			6.3.13. Índice de Maternidad (IMAT)
				6.3.13.1. Nacional
				6.3.13.2. Departamental
			6.3.14. Índice de Frizz (IF)
				6.3.14.1. Nacional
				6.3.14.2. Departamental
			6.3.15. Índice de Sundbard (IS)
				6.3.15.1. Nacional
				6.3.15.2. Departamental
			6.3.16. Índice de Burgdofer (IB)
				6.3.16.1. Nacional
				6.3.16.2. Departamental
			6.3.17. Índice de Generacional de Ancianos (IGA)
				6.3.17.1. Nacional
				6.3.17.2. Departamental
			6.3.18. Índice de Vejez (IV)
				6.3.18.1. Nacional
				6.3.18.2. Departamental
			6.3.19. Índice de Sobreenvejecimiento (ISE)
				6.3.19.1. Nacional
				6.3.19.2. Departamental
			6.3.20. Índice de Juventud (IJ)
				6.3.20.1. Nacional
				6.3.20.2. Departamental
			6.3.21. Índice de Infancia (II)
				6.3.21.1. Nacional
				6.3.21.2. Departamental
			6.3.22. Índice de Potencialidad de Reproducción Femenina(IPRF)
				6.3.22.1. Nacional
				6.3.22.2. Departamental
*/
********************************************************************************

	**# Formato imágenes
	
	graph set window fontface "Arial Narrow"
	grstyle init
	grstyle set legend 5, nobox 
	grstyle set graphsize 1200 900
	grstyle set size 15pt: heading
	grstyle set size 15pt: subheading axis_title 
	grstyle set size 15pt: tick_label 
	grstyle set size 15pt: text_option
	
	**# Notas, fuentes y ejes
	
	global nota1	"{bf:[1] Nota:} Las proyecciones de datos para el período 2005-2011 se basan en el Censo Nacional de Población y Vivienda (CNPV) 2001."
	global nota11	"{bf:[1] Nota:} De 2012 a 2023, las proyecciones se fundamentan en estimaciones poblacionales de la Revisión 2020."
	global nota2	"{bf:[2] Nota:} De 2012 a 2023, las proyecciones se fundamentan en estimaciones poblacionales de la Revisión 2020."
	global nota21	"{bf:[2] Nota:} La Revisión 2020 se actualizó en base a información provista por la Encuesta de Demografía y Salud 2016 e información de registros administrativos a nivel municipal."
	global nota3	"{bf:[3] Nota:} La Revisión 2020 se actualizó en base a información provista por la Encuesta de Demografía y Salud 2016 e información de registros administrativos a nivel municipal."
	global fuente	"{bf:Fuente:}  Sistema Nacional de Información en Salud - Vigilancia Epidemiológica (SNIS-VE), Ministerio de Salud y Deportes (MSyD) e Instituto Nacional de Estadísticas (INE)."
	global fuente1	"{bf:Fuente:} Elaboración Observatorio IISEC-UCB."
	global fuente2	"{bf:Fuente:} Elaboración Observatorio IISEC-UCB en base a datos del SNIS-VE, MSyD e INE."
	global eje		"Número de Mujeres en Edad Fértil (MEF)"
	global eje1		"Porcentaje (%)"	
	global eje2		"Número de embarazos"
	global eje3		"Número de partos"
	global eje4		"Número de abortos"
	global eje5		"Número de nacimientos"
	global eje6		"Número de Hijos Nacidos Vivos"
	global eje7		"Número de Hijos Nacidos Muertos"
	global eje8		"Número de abortos por cada 1,000 Mujeres en Edad Fértil"	
	global eje9		"Número de Hijos Nacidos Vivos por cada 1,000 Mujeres en Edad Fértil"	
	global eje10	"Número de defunciones fetales por cada 1,000 Hijos Nacidos Vivos"
	global eje11	"Número de embarazos por cada 1,000 Mujeres en Edad Fértil"
	global eje12    "Número de Hijos Nacidos Vivos por cada 1,000 habitantes"
	global eje13    "Número de hombres por cada 100 mujeres"
	global eje14 	"Número de personas dependientes por cada 100 personas en edad activa"
	global eje15 	"Número de adultos mayores por cada 100 niños y jóvenes"
	global eje16 	"Número de jóvenes dependientes por cada 100 personas en edad activa"
	global eje17 	"Número de adultos mayores por cada 100 personas en edad activa"
	global eje18 	"Número de jóvenes por cada 100 personas mayores de 65 y más años"
	global eje19 	"Edad mediana en años"
	global eje20 	"Edad media en años"
	global eje21 	"Número de personas que se retiran por cada 100 personas que ingresan"
	global eje22 	"Número de personas maduras por cada 100 personas jóvenes"
	global eje23 	"Número de niños pequeños de 0 a 4 años por cada 100 Mujeres en Edad Fértil"
	global eje24 	"Número de personas de 0 a 19 años por cada 100 personas de 30 a 49 años"
	global eje25 	"Número de jóvenes por cada 100 personas maduras"
	global eje26 	"Número de personas de 35 a 64 años por cada 100 personas de 65 y más años"
	global eje27 	"Número de personas mayores de 80 años por cada 100 mayores de 65 años"
	global eje28 	"Número de mujeres de 20 a 34 años por cada 100 mujeres entre 35 a 49 años"
	
	**# Directorio
	
	if ("`c(username)'" == "User") {   // Arleth

	global path		"L:\Unidades compartidas\1_INDICADORES_ODSB_2022\01COPIA_IISEC_ODSB"
	global work 	"$path\INDICADORES\6_SALUD"
	global in 		"$path\!EH_ARMONIZADA\_salud"
	global do 		"$work\_do"
	global gph		"$work\_gph\DemografíaSaludSexualyReproductiva"
	global xlsx		"$work\_xlsx"
	global out		"$work\_out"
	}
	
		if ("`c(username)'" == "Alejandra Lafuente") {   // Arleth

	global path		"I:\Unidades compartidas\1_INDICADORES_ODSB_2022\01COPIA_IISEC_ODSB"
	global work 	"$path\INDICADORES\6_SALUD"
	global in 		"$path\!EH_ARMONIZADA\_salud"
	global do 		"$work\_do"
	global gph		"$work\_gph\DemografíaSaludSexualyReproductiva"
	global xlsx		"$work\_xlsx"
	global out		"$work\_out"
	}

		if ("`c(username)'" == "DELL") {   // Arleth

	global path		"G:\Unidades compartidas\1_INDICADORES_ODSB_2022\01COPIA_IISEC_ODSB"
	global work 	"$path\INDICADORES\6_SALUD"
	global in 		"$path\!EH_ARMONIZADA\_salud"
	global do 		"$work\_do"
	global gph		"$work\_gph\DemografíaSaludSexualyReproductiva"
	global xlsx		"$work\_xlsx"
	global out		"$work\_out"
	}
	
	**# 6.1.1. Número de Mujeres en Edad Fértil (MEF)
	
	import excel "$in\06_001_01.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.1.1. Nacional

	set scheme white_tableau

	format %4.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(2330200(160000)3130200, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_01_01.png", replace
	
	**# 6.1.1.2. Departamental
	
	import excel "$in\06_001_01.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(13000(450500)910000, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje") title("", box color(black) span)

	gr export "$gph/06_001_01_02.png", replace	
	
	**# 6.1.2. Proporción de Mujeres en Edad Fértil (MEF)
	
	import excel "$in\06_001_02.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.2.1. Nacional
	
	set scheme white_tableau
	
	format %4.2fc Bolivia
	
	twoway (connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel (Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ylab(48(1)53, format(%9.0fc)) ///
	xtitle("") ytitle("$eje1") note("$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)
	gr export "$gph/06_001_02_01.png", replace

	**# 6.1.2.2. Departamental

	import excel "$in\06_001_02.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)), ///
    by(Departamento_order, note("$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(43(5)55, format(%9.0fc)) xlab(2012(1)2023, angle(45)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_001_02_02.png", replace
	
	**# 6.1.3. Número de embarazos
	
	import excel "$in\06_001_03.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.3.1. Nacional

	set scheme white_tableau

	format %9.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(250000(16000)330000, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje2") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_03_01.png", replace
	
	**# 6.1.3.2. Departamental
	
	import excel "$in\06_001_03.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(2000(45000)92000, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje2") title("", box color(black) span)

	gr export "$gph/06_001_03_02.png", replace	
	
	**# 6.1.4. Número de partos
	
	import excel "$in\06_001_04.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.4.1. Nacional

	set scheme white_tableau

	format %4.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(220000(15000)295000, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje3") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_04_01.png", replace
	
	**# 6.1.4.2. Departamental
	
	import excel "$in\06_001_04.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(2000(44000)92000, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje3") title("", box color(black) span)

	gr export "$gph/06_001_04_02.png", replace	
	
	**# 6.1.5. Número de abortos
	
	import excel "$in\06_001_05.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.5.1. Nacional

	set scheme white_tableau

	format %4.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(10000(9000)55000, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje4") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_05_01.png", replace
	
	**# 6.1.5.2. Departamental
	
	import excel "$in\06_001_05.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(200(6300)13000, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje4") title("", box color(black) span)

	gr export "$gph/06_001_05_02.png", replace	
	
	**# 6.1.6. Proporción de Partos y Abortos sobre total de Embarazos
	
	import excel "$in\06_001_06.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.6.1. Nacional

	set scheme white_tableau

	graph bar (asis) Valor, over(Tipo) over(Año, label(angle(45))) /// 
    stack asyvars percent /// 
    ytitle("$eje1") xtitle() /// 
	ylabel(0(20)100, format(%9.0f)) /// 
    blabel(bar, position(center) size(small) format(%9.0f)) /// 
    legend(label(1 "Abortos") label(2 "Partos") ///
           position(6) cols(2) size(small)) /// 
    note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span)

	graph export "$gph/06_001_06_01.png", replace
	
    **# 6.1.6.2. Departamental
	
	import excel "$in\06_001_06.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	graph bar (asis) Valor if Departamento_order <= 6, over(Tipo) over(Año, label(nolabel)) /// 
    stack asyvars ///  
    ytitle("") /// 
    ylabel(0(50)100, format(%9.0f)) /// 
    by(Departamento_order, title("") col(3) note("") legend(off) ///
    xrescale) ///
    name(g1, replace)

	graph bar (asis) Valor if Departamento_order >= 7, over(Tipo) over(Año, label(angle(90))) /// 
    stack asyvars /// 
    legend(label(1 "Abortos") label(2 "Partos") cols(2)) /// 
    ytitle("") /// 
    ylabel(0(50)100, format(%9.0f)) /// 
    by(Departamento_order, title("") col(3) note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
xrescale) ///
    name(g2, replace)

	graph combine g1 g2, cols(1) imargin(0 0 0 0) 

	graph save "06_001_06_02.gph", replace
	gr export "$gph/06_001_06_02.png", replace
	
	**# 6.1.7. Número de nacimientos
	
	import excel "$in\06_001_07.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.7.1. Nacional

	set scheme white_tableau

	format %4.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(230000(13000)295000, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje5") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_07_01.png", replace
	
	**# 6.1.7.2. Departamental
	
	import excel "$in\06_001_07.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(2000(41500)85000, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje5") title("", box color(black) span)

	gr export "$gph/06_001_07_02.png", replace	
	
	**# 6.1.8. Número de Hijos Nacidos Vivos
	
	import excel "$in\06_001_08.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.8.1. Nacional

	set scheme white_tableau

	format %4.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(230000(13000)295000, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje6") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_08_01.png", replace
	
	**# 6.1.8.2. Departamental
	
	import excel "$in\06_001_08.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(2000(41500)85000, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje6") title("", box color(black) span)

	gr export "$gph/06_001_08_02.png", replace	
	
	**# 6.1.9. Número de Hijos Nacidos Muertos
	
	import excel "$in\06_001_09.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.9.1 Nacional

	set scheme white_tableau

	format %4.3fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(1800(600)4800, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje7") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_001_09_01.png", replace
	
	**# 6.1.9.2. Departamental
	
	import excel "$in\06_001_09.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(10(750)1510, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje7") title("", box color(black) span)

	gr export "$gph/06_001_09_02.png", replace		
	
	**# 6.1.10. Proporción de HNV e HNM sobre total de Nacimientos
	
	import excel "$in\06_001_10.xlsx", sheet("_in") firstrow clear
	
	**# 6.1.10.1. Nacional

	set scheme white_tableau

	graph bar (asis) Valor, over(Tipo) over(Año, label(angle(45))) /// 
    stack asyvars percent /// 
    ytitle("$eje1") xtitle() /// 
	ylabel(0(20)100, format(%9.0f)) /// 
    blabel(bar, position(center) size(small) format(%9.0f)) /// 
    legend(label(1 "Hijos Nacidos Muertos") label(2 "Hijos Nacidos Vivos") ///
           position(6) cols(2) size(small)) /// 
    note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span)

	graph export "$gph/06_001_10_01.png", replace
	
    **# 6.1.10.2. Departamental
	
	import excel "$in\06_001_10.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	graph bar (asis) Valor if Departamento_order <= 6, over(Tipo) over(Año, label(nolabel)) /// 
    stack asyvars ///  
    ytitle("") /// 
    ylabel(0(50)100, format(%9.0f)) /// 
    by(Departamento_order, title("") col(3) note("") legend(off) ///
    xrescale) ///
    name(g1, replace)

	graph bar (asis) Valor if Departamento_order >= 7, over(Tipo) over(Año, label(angle(90))) /// 
    stack asyvars /// 
    legend(label(1 "Hijos Nacidos Muertos ") label(2 "Hijos Nacidos Vivos") cols(2)) /// 
    ytitle("") /// 
    ylabel(0(50)100, format(%9.0f)) /// 
    by(Departamento_order, title("") col(3) note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
xrescale) ///
    name(g2, replace)

	graph combine g1 g2, cols(1) imargin(0 0 0 0) 

	graph save "06_001_10_02.gph", replace
	gr export "$gph/06_001_10_02.png", replace
	
	**# 6.2.1. Tasa de Aborto General (TAG)
	
	import excel "$in\06_002_01.xlsx", sheet("_in") firstrow clear
	
	**# 6.2.1.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(5(3)20, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje8") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_002_01_01.png", replace
	
	**# 6.2.1.2. Departamental

	import excel "$in\06_002_01.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(0(20)40, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje8") title("", box color(black) span)

	gr export "$gph/06_002_01_02.png", replace		
	
	**# 6.2.2. Tasa de Fecundidad General (TFG)
	
	import excel "$in\06_002_02.xlsx", sheet("_in") firstrow clear
	
	**# 6.2.2.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(65(14)135, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje9") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_002_02_01.png", replace
	
	**# 6.2.2.2. Departamental

	import excel "$in\06_002_02.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(60(60)180, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje9") title("", box color(black) span)

	gr export "$gph/06_002_02_02.png", replace		

	**# 6.2.3. Tasa de Mortalidad Fetal (TMF)
	
	import excel "$in\06_002_03.xlsx", sheet("_in") firstrow clear
	
	**# 6.2.3.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(7(2)17, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje10") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_002_03_01.png", replace
	
	**# 6.2.3.2. Departamental
	
	import excel "$in\06_002_03.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(4(10)24, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje10") title("", box color(black) span)

	gr export "$gph/06_002_03_02.png", replace	
	
	**# 6.2.4. Tasa Estimada de Embarazo (TEE)
	
	import excel "$in\06_002_04.xlsx", sheet("_in") firstrow clear
	
	**# 6.2.4.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(70(15)145, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje11") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_002_04_01.png", replace
	
	**# 6.2.4.2. Departamental
	
	import excel "$in\06_002_04.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(70(65)200, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje11") title("", box color(black) span)

	gr export "$gph/06_002_04_02.png", replace	
	
	**# 6.3.1. Tasa Bruta de Natalidad (TBN)
	
	import excel "$in\06_003_01.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.1.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(17(3)32, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje12") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_01_01.png", replace
	
	**# 6.3.1.2. Departamental
	
	import excel "$in\06_003_01.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(16(11)38, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje12") title("", box color(black) span)

	gr export "$gph/06_003_01_02.png", replace	
	
	**# 6.3.2. Índice de Masculinidad (IM)
	
	import excel "$in\06_003_02.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.2.1. Nacional
	
	set scheme white_tableau
	
	format %4.2fc Bolivia
	
	twoway (connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel (Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ylab(98(1)103, format(%9.0fc)) ///
	xtitle("") ytitle("$eje13") note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)
	gr export "$gph/06_003_02_01.png", replace
	
	**# 6.3.2.2. Departamental
	
	import excel "$in\06_003_02.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") mlabp(12) mlabs(*.90) msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(95(15)125, format(%9.0fc)) xlab(2012(1)2023, angle(45)) ///
    xtitle("") ytitle("$eje13") title("", box color(black) span)

	gr export "$gph/06_003_02_02.png", replace

	**# 6.3.3. Tasa de Creciemiento Poblacional (TCP)
	
	import excel "$in\06_003_03.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.3.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(1(0.3)2.5, format(%9.2fc)) ///
	xtitle("") ///
	ytitle("$eje1") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_03_01.png", replace
	
	**# 6.3.3.2. Departamental
	
	import excel "$in\06_003_03.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(0(2.5)5, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_03_02.png", replace	
	
	**# 6.3.4. Distribución de la Población por Grupos Etarios (DPGE)
	
	**# 6.3.4.1. Nacional
	
	import excel "$in\06_003_04.xlsx", sheet("_in") firstrow clear

	set scheme white_tableau

	graph bar (asis) Valor, over(Tipo) over(Año, label(angle(45))) /// 
    stack asyvars percent /// 
    ytitle("$eje1") xtitle() /// 
	ylabel(0(20)100, format(%9.0f)) /// 
    blabel(bar, position(center) size(small) format(%9.0f)) /// 
    legend(label(1 "0-4 años") label(2 "5-14 años") label(3 "15-64 años") label(4 "65 años y más") /// 
	position(6) cols(4) size(small)) /// 
    note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span)

	graph export "$gph/06_003_04_01.png", replace
	
	**# 6.3.4.2. Departamental
	
	import excel "$in\06_003_04.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	graph bar (asis) Valor if Departamento_order <= 6, over(Tipo) over(Año, label(nolabel)) /// 
    stack asyvars ///  
    ytitle("") /// 
    ylabel(0(50)100, format(%9.0f)) /// 
    by(Departamento_order, title("") col(3) note("") legend(off) ///
    xrescale) ///
    name(g1, replace)

	graph bar (asis) Valor if Departamento_order >= 7, over(Tipo) over(Año, label(angle(90))) /// 
    stack asyvars /// 
    legend(label(1 "0-4 años") label(2 "5-14 años") label(3 "15-64 años") label(4 "65 años y más") cols(4)) /// 
    ytitle("") /// 
    ylabel(0(50)100, format(%9.0f)) /// 
    by(Departamento_order, title("") col(3) note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
xrescale) ///
    name(g2, replace)

	graph combine g1 g2, cols(1) imargin(0 0 0 0) 

	graph save "06_003_04_02.gph", replace
	gr export "$gph/06_003_04_02.png", replace
	
	**# 6.3.5. Índice de Dependencia Potencial (IDP)
	
	import excel "$in\06_003_05.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.5.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(50(6)80, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje14") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_05_01.png", replace
	
	**# 6.3.5.2. Departamental

	import excel "$in\06_003_05.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(40(20)80, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje14") title("", box color(black) span)

	gr export "$gph/06_003_05_02.png", replace		
	
	**# 6.3.6. Índice de Envejecimiento (IE)
	
	import excel "$in\06_003_06.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.6.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(5(5)30, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje15") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_06_01.png", replace
	
	**# 6.3.6.2. Departamental

	import excel "$in\06_003_06.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(5(15)35, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje15") title("", box color(black) span)

	gr export "$gph/06_003_06_02.png", replace		
	
	**# 6.3.7. Índice de Dependencia Juvenil (IDJ)
	
	import excel "$in\06_003_07.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.7.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(40(6)70, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje16") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_07_01.png", replace
	
	**# 6.3.7.2. Departamental

	import excel "$in\06_003_07.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(35(25)85, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje16") title("", box color(black) span)

	gr export "$gph/06_003_07_02.png", replace	
	
	**# 6.3.8. Índice de Dependencia Senil (IDS)
	
	import excel "$in\06_003_08.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.8.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(5(2)15, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje17") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_08_01.png", replace
	
	**# 6.3.8.2. Departamental

	import excel "$in\06_003_08.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(0(10)20, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje17") title("", box color(black) span)

	gr export "$gph/06_003_08_02.png", replace	
	
	**# 6.3.9. Edad Mediana de la Población (EMDP)
	
	import excel "$in\06_003_09.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.9.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(22.5(1)27.5, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje19") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_09_01.png", replace
	
	**# 6.3.9.2. Departamental

	import excel "$in\06_003_09.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(19(5)29, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje19") title("", box color(black) span)

	gr export "$gph/06_003_09_02.png", replace			
	
	**# 6.3.10. Edad Media de la Población (EMP)
	
	import excel "$in\06_003_10.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.10.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(26(1)31, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje20") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_10_01.png", replace
	
	**# 6.3.10.2. Departamental

	import excel "$in\06_003_10.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(23(5)33, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje20") title("", box color(black) span)

	gr export "$gph/06_003_10_02.png", replace	
	
	**# 6.3.11. Índice de Reemplazamiento de la Población en Edad Activa (IRPEA)
	
	import excel "$in\06_003_11.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.11.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(24(2)34, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje21") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_11_01.png", replace
	
	**# 6.3.11.2. Departamental

	import excel "$in\06_003_11.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(15(13)41, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje21") title("", box color(black) span)

	gr export "$gph/06_003_11_02.png", replace
	
	**# 6.3.11a. Índice de Reemplazamiento de la Población en Edad Activa (IRPEA) según sexo

	import excel "$in\06_003_11.xlsx", sheet("_in2") firstrow clear
	
	**# 6.3.11.3. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia1
	format %4.2fc Bolivia2

	twoway /// 
	(connected Bolivia1 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia1)) /// 
	(connected Bolivia2 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia2)), /// 
	xlab(2012(1)2023, angle(45)) /// 
	ylab(20(3)35, format(%9.0fc)) /// 
	xtitle("") /// 
	ytitle("$eje1") /// 
	legend(label(1 "IRPEA hombres") label(2 "IRPEA mujeres") /// 
	position(6) cols(2) size(small)) /// 
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) /// 

	gr export "$gph/06_003_11_03.png", replace	
	
	**# 6.3.11.4. Departamental

	import excel "$in\06_003_11.xlsx", sheet("_in3") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor1 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
	by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span)) /// 
	legend(order(1 "IRPEA hombres" 2 "IRPEA mujeres") cols(9)) ///
    ylab(10(15)40, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_11_04.png", replace
	
	**# 6.3.12. Índice de Estructura de la Población en Edad Activa (IEPEA)

	import excel "$in\06_003_12.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.12.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(45(2)55, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje22") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_12_01.png", replace
	
	**# 6.3.12.2. Departamental

	import excel "$in\06_003_12.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(32(15)62, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje22") title("", box color(black) span)

	gr export "$gph/06_003_12_02.png", replace

	**# 6.3.12a. Índice de Estructura de la Población en Edad Activa (IEPEA) según sexo

	import excel "$in\06_003_12.xlsx", sheet("_in2") firstrow clear
	
	**# 6.3.12.3. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia1
	format %4.2fc Bolivia2

	twoway /// 
	(connected Bolivia1 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia1)) /// 
	(connected Bolivia2 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia2)), /// 
	xlab(2012(1)2023, angle(45)) /// 
	ylab(40(4)60, format(%9.0fc)) /// 
	xtitle("") /// 
	ytitle("$eje1") /// 
	legend(label(1 "IEPEA hombres") label(2 "IEPEA mujeres") /// 
	position(6) cols(2) size(small)) /// 
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) /// 

	gr export "$gph/06_003_12_03.png", replace	
	
	**# 6.3.12.4. Departamental

	import excel "$in\06_003_12.xlsx", sheet("_in3") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor1 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
	by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span)) /// 
	legend(order(1 "IRPEA hombres" 2 "IRPEA mujeres") cols(9)) ///
    ylab(30(20)70, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_12_04.png", replace
	
	**# 6.3.13. Índice de Maternidad (IMAT)

	import excel "$in\06_003_13.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.13.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(36(4)56, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje23") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_13_01.png", replace
	
	**# 6.3.13.2. Departamental
	
	import excel "$in\06_003_13.xlsx", sheet("_in1") firstrow clear
	
	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(30(25)80, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje23") title("", box color(black) span)

	gr export "$gph/06_003_13_02.png", replace	

	**# 6.3.14. Índice de Friz (IF)

	import excel "$in\06_003_14.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.14.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(145(10)195, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje24") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_14_01.png", replace
	
	**# 6.3.14.2. Departamental

	import excel "$in\06_003_14.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(132(65)262, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje24") title("", box color(black) span)

	gr export "$gph/06_003_14_02.png", replace
	
	**# 6.3.15. Índice de Sundbarg (IS)

	import excel "$in\06_003_15.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.15.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia1
	format %4.2fc Bolivia2

	twoway /// 
	(connected Bolivia1 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia1)) /// 
	(connected Bolivia2 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia2)), /// 
	xlab(2012(1)2023, angle(45)) /// 
	ylab(30(8)70, format(%9.0fc)) /// 
	xtitle("") /// 
	ytitle("$eje1") /// 
	legend(label(1 "IS jóvenes") label(2 "IS mayores") /// 
	position(6) cols(2) size(small)) /// 
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) /// 

	gr export "$gph/06_003_15_01.png", replace	
	
	**# 6.3.15.2. Departamental

	import excel "$in\06_003_15.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor1 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
	(connected Valor2 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor1 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor2 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
	by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span)) /// 
	legend(order(1 "IS jóvenes" 2 "IS mayores") cols(9)) ///
    ylab(15(37.5)90, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_15_02.png", replace
	
	**# 6.3.16. Índice de Burgdofer (IB)

	import excel "$in\06_003_16.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.16.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(115(9)160, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje25") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_16_01.png", replace
	
	**# 6.3.16.2. Departamental

	import excel "$in\06_003_16.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(95(75)245, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje25") title("", box color(black) span)

	gr export "$gph/06_003_16_02.png", replace
	
	**# 6.3.17. Índice Generacional de Ancianos (IGA)

	import excel "$in\06_003_17.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.17.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(360(10)410, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje26") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_17_01.png", replace
	
	**# 6.3.17.2. Departamental

	import excel "$in\06_003_17.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(290(257.5)805, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje26") title("", box color(black) span)

	gr export "$gph/06_003_17_02.png", replace

	**# 6.3.18. Índice de Vejez (IV)

	import excel "$in\06_003_18.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.18.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(4(0.9)8.5, format(%9.2fc)) ///
	xtitle("") ///
	ytitle("$eje1") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_18_01.png", replace
	
	**# 6.3.18.2. Departamental

	import excel "$in\06_003_18.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(1(4.5)10, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_18_02.png", replace

	**# 6.3.19. Índice de Sobreenvejecimiento (ISE)

	import excel "$in\06_003_19.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.19.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(19(1)24, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje27") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_19_01.png", replace
	
	**# 6.3.19.2. Departamental

	import excel "$in\06_003_19.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(10(10)30, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje27") title("", box color(black) span)

	gr export "$gph/06_003_19_02.png", replace

	**# 6.3.20. Índice de Juventud (IJ)

	import excel "$in\06_003_20.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.20.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(25.9(0.6)28.9, format(%9.2fc)) ///
	xtitle("") ///
	ytitle("$eje1") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_20_01.png", replace
	
	**# 6.3.20.2. Departamental

	import excel "$in\06_003_20.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(23(3.5)30, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_20_02.png", replace
	
	**# 6.3.21. Índice de Infancia (II)

	import excel "$in\06_003_21.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.21.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	gen Bolivia_2005_2011 = Bolivia if Año <= 2011
	gen Bolivia_2012_2023 = Bolivia if Año >= 2012

	twoway ///
	(connected Bolivia_2005_2011 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2005_2011)) ///
	(connected Bolivia_2012_2023 Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia_2012_2023)), ///
	xlab(2005(1)2023, angle(45)) ///
	ylab(26(3)41, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje1") ///
	note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_21_01.png", replace
	
	**# 6.3.21.2. Departamental

	import excel "$in\06_003_21.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	gen Valor_2005_2011 = Valor if Año <= 2011
	gen Valor_2012_2023 = Valor if Año >= 2012

	twoway ///
    (connected Valor_2005_2011 Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Chuquisaca", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "LaPaz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Cochabamba", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Oruro", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Potosí", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Tarija", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "SantaCruz", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Beni", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)) ///
    (connected Valor_2005_2011 Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor_2012_2023 Año if Departamento == "Pando", lcolor("255 227 20") mcolor("255 227 20") msymbol(circle)), ///
    by(Departamento_order, note("$nota1" "$nota2" "$nota3" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(25(10)45, format(%9.0fc)) ///
    xlab(2005(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje1") title("", box color(black) span)

	gr export "$gph/06_003_21_02.png", replace

	**# 6.3.22. Índice de Potencialidad de Reproducción Femenina (IPRF)

	import excel "$in\06_003_22.xlsx", sheet("_in") firstrow clear
	
	**# 6.3.22.1. Nacional
	
	set scheme white_tableau

	format %4.2fc Bolivia

	twoway ///
	(connected Bolivia Año, mlabp(12) mlabs(*.90) msymbol(circle) mlabel(Bolivia)), ///
	xlab(2012(1)2023, angle(45)) ///
	ylab(135(4)155, format(%9.0fc)) ///
	xtitle("") ///
	ytitle("$eje28") ///
	note("$nota11" "$nota21" "$fuente2", size(vsmall) span) ///
	legend(off)

	gr export "$gph/06_003_22_01.png", replace
	
	**# 6.3.22.2. Departamental

	import excel "$in\06_003_22.xlsx", sheet("_in1") firstrow clear

	set scheme white_viridis
	
	gen Departamento_order = .
	replace Departamento_order = 1 if Departamento == "Chuquisaca"
	replace Departamento_order = 2 if Departamento == "LaPaz"
	replace Departamento_order = 3 if Departamento == "Cochabamba"
	replace Departamento_order = 4 if Departamento == "Oruro"
	replace Departamento_order = 5 if Departamento == "Potosí"
	replace Departamento_order = 6 if Departamento == "Tarija"
	replace Departamento_order = 7 if Departamento == "SantaCruz"
	replace Departamento_order = 8 if Departamento == "Beni"
	replace Departamento_order = 9 if Departamento == "Pando"

	label define Departamento_order_lbl 1 "Chuquisaca" 2 "La Paz" 3 "Cochabamba" 4 "Oruro" 5 "Potosí" 6 "Tarija" 7 "Santa Cruz" 8 "Beni" 9 "Pando"
	label values Departamento_order Departamento_order_lbl

	twoway ///
    (connected Valor Año if Departamento == "Chuquisaca", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "LaPaz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Cochabamba", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Oruro", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Potosí", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Tarija", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "SantaCruz", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Beni", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)) ///
    (connected Valor Año if Departamento == "Pando", lcolor("108 171 44") mcolor("108 171 44") msymbol(circle)), ///
    by(Departamento_order, note("$nota11" "$nota21" "$fuente2", size(vsmall) span) legend(off)) ///
    ylab(115(37.5)190, format(%9.0fc)) ///
    xlab(2012(1)2023, angle(90)) ///
    xtitle("") ytitle("$eje28") title("", box color(black) span)

	gr export "$gph/06_003_22_02.png", replace
