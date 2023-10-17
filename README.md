# U1

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
