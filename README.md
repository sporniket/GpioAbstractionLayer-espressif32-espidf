# GpioAbstractionLayer-espressif32-espidf
C++ library for PlatformIO, implementation of the GpioAbstractionLayer for the espressif32 platform, using the espidf framework

## LICENSE

GPL v3

## What's new

### v0.0.2

* Adapt to recent idf version

### v0.0.1

Initial publishing, extracted from working code.


## Typical application

```cpp
#include "GeneralPurposeInputOutput.hpp"
#include "DigitalInputOutputEsp32.hpp"

extern "C" {
	void app_main(void);
}

GeneralPurposeInputOutput* gpio ;

void app_main(void) {
	// setup

	gpio = (new GeneralPurposeInputOutput())
		->withDigital(new DigitalInputOutputEsp32()) ;

    gpio->getDigital()->setup(WHATEVER_PIN1, WRITE) ;
    gpio->getDigital()->setup(WHATEVER_PIN2, READ) ;

    // use
    gpio->getDigital()->write(WHATEVER_PIN1, true)
    gpio->getDigital()->read(WHATEVER_PIN2) ;

}

```