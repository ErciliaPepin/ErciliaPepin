<?php
// Cargar la librería PhpSpreadsheet
require 'vendor/autoload.php';
use PhpOffice\PhpSpreadsheet\Spreadsheet;
use PhpOffice\PhpSpreadsheet\Writer\Xlsx;

// Crear nuevo archivo Excel o cargar el existente
$spreadsheet = new Spreadsheet();
$sheet = $spreadsheet->getActiveSheet();

// Obtener datos del formulario
$nombres = $_POST['nombres'];
$apellidos = $_POST['apellidos'];
$edad = $_POST['edad'];
$celular = $_POST['celular'];
$situaciones = $_POST['situaciones'];
$neae = $_POST['neae'];

// Escribir los datos en el archivo Excel
$sheet->setCellValue('A1', 'Nombres');
$sheet->setCellValue('B1', 'Apellidos');
$sheet->setCellValue('C1', 'Edad');
$sheet->setCellValue('D1', 'Celular');
$sheet->setCellValue('E1', 'Situaciones');
$sheet->setCellValue('F1', 'NEAE');

$sheet->setCellValue('A2', $nombres);
$sheet->setCellValue('B2', $apellidos);
$sheet->setCellValue('C2', $edad);
$sheet->setCellValue('D2', $celular);
$sheet->setCellValue('E2', $situaciones);
$sheet->setCellValue('F2', $neae);

// Guardar el archivo Excel
$writer = new Xlsx($spreadsheet);
$writer->save('estudiantes.xlsx');
?>

