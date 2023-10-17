import Foundation
class Complex {
  var real: Double
  var imaginary: Double
  init(real: Double, imaginary: Double) {
    self.real = real
    self.imaginary = imaginary
  }
  func incrementBy(real: Double) {
    self.real += real
  }
  func incrementBy(imaginary: Double) {
    self.imaginary += imaginary
  }
  func incrementBy(complex: Complex) {
    self.real += complex.real
    self.imaginary += complex.imaginary
  }
  func multiplyBy(complex: Complex) {
    let real = self.real * complex.real - self.imaginary * complex.imaginary
    let imaginary = self.real * complex.imaginary + self.imaginary * complex.real
    self.real = real
    self.imaginary = imaginary
  }
  func rotateBy(angle: Double) {
    let real = self.real * cos(angle) - self.imaginary * sin(angle)
    let imaginary = self.real * sin(angle) + self.imaginary * cos(angle)
    self.real = real
    self.imaginary = imaginary
  }
  func plus(complex: Complex) -> Complex {
    return Complex(real: self.real + complex.real, imaginary: self.imaginary + complex.imaginary)
  }
}
// Einlesen einer komplexen Zahl über die Konsole.
print("Bitte geben Sie eine komplexe Zahl in der Form 'a+bi' ein:")
guard let input = readLine() else {
  fatalError("Fehler beim Einlesen der Eingabe.")
}
// Parsen der Eingabe in eine komplexe Zahl.
let complex = Complex(input)
// Ausgabe der komplexen Zahl.
print("Die eingegebene komplexe Zahl ist \(complex).")
// Addieren der komplexen Zahl (1.2 + 2.4 i).
complex.incrementBy(complex: Complex(real: 1.2, imaginary: 2.4))
// Ausgabe der komplexen Zahl.
print("Die komplexe Zahl nach dem Addieren von (1.2 + 2.4 i) ist \(complex).")
// Erhöhen des Realteils um 2.2.
complex.incrementBy(real: 2.2)
