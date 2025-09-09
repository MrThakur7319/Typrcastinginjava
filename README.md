# Typrcastinginjava
public class Typecasting {
/**
     * Main method demonstrating various typecasting scenarios
     * @param args command line arguments
     */
    public static void main(String[] args) {
        
   // ===== IMPLICIT CASTING (WIDENING CONVERSION) =====
        // Automatic conversion from smaller to larger data type
        // No data loss occurs during this conversion
        
  int intNum = 100;           // Integer value
        double doubleNum = intNum;  // Implicit casting: int -> double
        System.out.println("implicit casting(int to double):" + doubleNum);
        // Result: 100.0 (integer converted to double automatically)
        
  // ===== EXPLICIT CASTING (NARROWING CONVERSION) =====
        // Manual conversion from larger to smaller data type
        // May result in data loss or precision loss
        
  double d = 99.00;        // Double value with decimal
        int i = (int)d;          // Explicit casting: double -> int (truncates decimal)
        System.out.println("explicit casting(double to int):" + i);
        // Result: 99 (decimal part .00 is lost)
         // ===== BYTE TO INT IMPLICIT CASTING =====
        // byte is smaller than int, so automatic conversion happens
         byte b = 10;             // byte value (-128 to 127 range)
        int num = b;             // Implicit casting: byte -> int
        System.out.println("byte to int(implicit):" + num);
        // Result: 10 (no data loss, byte fits perfectly in int)
          // ===== INT TO BYTE EXPLICIT CASTING =====
        // int is larger than byte, manual casting required
        // WARNING: This can cause data overflow!
         int bigNum = 130;                    // int value (larger than byte max of 127)
        byte smallNum = (byte)bigNum;        // Explicit casting: int -> byte
        System.out.println("int to byte (explicit):" + smallNum);
        // Result: -126 (overflow occurred! 130 > 127, so it wraps around)
         /*
         * EXPLANATION OF BYTE OVERFLOW:
         * - byte range: -128 to 127
         * - 130 is outside this range
         * - Java uses two's complement representation
         * - 130 becomes -126 due to overflow wraparound
         * 
         * CASTING RULES SUMMARY:
         * - Implicit: Safe conversions (smaller -> larger)
         * - Explicit: Potentially unsafe (larger -> smaller)
         * - Always be careful with explicit casting to avoid data loss
         */
    }
}
