import Foundation

// Funktion zum Einlesen einer komplexen Zahl von der Konsole
func readComplex() -> Complex {
    print("Geben Sie den Realteil ein:")
    let real = Double(readLine()!) ?? 0.0
    print("Geben Sie den Imaginärteil ein:")
    let imaginary = Double(readLine()!) ?? 0.0
    return Complex(real: real, imaginary: imaginary)
}

// Einlesen einer komplexen Zahl von der Konsole
print("Bitte geben Sie eine komplexe Zahl ein:")
var complexNumber = readComplex()

// Ausgabe zur Kontrolle
print("Eingegebene komplexe Zahl: \(complexNumber.real) + \(complexNumber.imaginary)i")

// Konstante komplexe Zahl (1.2 + 2.4i)
let addComplex = Complex(real: 1.2, imaginary: 2.4)

// Addieren der konstanten komplexen Zahl
complexNumber = complexNumber.plus(addComplex)
print("Nach Addition mit (1.2 + 2.4i): \(complexNumber.real) + \(complexNumber.imaginary)i")

// Erhöhen des Realteils um 2.2
complexNumber.incrementBy(realIncrement: 2.2)
print("Nach Erhöhung des Realteils um 2.2: \(complexNumber.real) + \(complexNumber.imaginary)i")

// Erhöhen des Imaginärteils um 0.6
complexNumber.incrementBy(imaginaryIncrement: 0.6)
print("Nach Erhöhung des Imaginärteils um 0.6: \(complexNumber.real) + \(complexNumber.imaginary)i")

// Multiplizieren mit (0.5 + 1.0i)
let multiplyComplex = Complex(real: 0.5, imaginary: 1.0)
complexNumber.multiplyBy(complex: multiplyComplex)
print("Nach Multiplikation mit (0.5 + 1.0i): \(complexNumber.real) + \(complexNumber.imaginary)i")

// Rotieren um den Winkel pi (Double.pi)
complexNumber.rotateBy(angle: Double.pi)
print("Nach Rotation um pi: \(complexNumber.real) + \(complexNumber.imaginary)i")

// Berechnen der Summe mit (0.2 + 0.9i)
let sumComplex = Complex(real: 0.2, imaginary: 0.9)
let result = complexNumber.plus(sumComplex)
print("Die Summe mit (0.2 + 0.9i) ist: \(result.real) + \(result.imaginary)i")
