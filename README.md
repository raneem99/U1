import Foundation

class Complex {
    var real: Double
    var imaginary: Double
    
    init(real: Double, imaginary: Double) {
        self.real = real
        self.imaginary = imaginary
    }
    
    func incrementBy(realIncrement: Double) {
        self.real += realIncrement
    }
    
    func incrementBy(imaginaryIncrement: Double) {
        self.imaginary += imaginaryIncrement
    }
    
    func incrementBy(complexIncrement: Complex) {
        self.real += complexIncrement.real
        self.imaginary += complexIncrement.imaginary
    }
    
    func multiplyBy(complex: Complex) {
        let newReal = (self.real * complex.real) - (self.imaginary * complex.imaginary)
        let newImaginary = (self.real * complex.imaginary) + (self.imaginary * complex.real)
        self.real = newReal
        self.imaginary = newImaginary
    }
    
    func rotateBy(angle: Double) {
        let currentMagnitude = sqrt((self.real * self.real) + (self.imaginary * self.imaginary))
        let currentPhase = atan2(self.imaginary, self.real)
        
        let newPhase = currentPhase + angle
        self.real = currentMagnitude * cos(newPhase)
        self.imaginary = currentMagnitude * sin(newPhase)
    }
    
    func plus(_ complex: Complex) -> Complex {
        let resultReal = self.real + complex.real
        let resultImaginary = self.imaginary + complex.imaginary
        return Complex(real: resultReal, imaginary: resultImaginary)
    }
}
