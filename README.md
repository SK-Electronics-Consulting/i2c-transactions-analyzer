
# I2C Transaction Analyzer

## Background
This extension is meant to allow a deep dive into I2C transactions, especially on a busy bus with multiple devices.
This comes form my experience of debugging designs, and trying to automate the tasks that I end up doing manually
or in my head as I'm reading all the I2C packets.

This is written to be a Saleae Logic Extension.  Obviously, the easiest way to do this would be having the Saleae 
hardware or a *.sal save file.  

## Basic Features
1. Will interpret I2C transactions based on the I2C standard, this means looking for the start and stop bits.
2. Will identify NAK'ed packets 

## Advanced Features
1. Will identify clock stretching events.  
2. Will filter transactions based on address.
3. Will Filter transactions based on register (for those chips where the 1st data byte is really an internal register 
   address)
4. Color coding writes and reads in the data terminal 
5. Pairing Reads with writes
6. Intelligently displaying sequential reads/writes (for those chips where multi-byte writes or reads just increment the internal register pointer)

## How to use



## Getting started

## Open Questions / TODO
1. Is it possible to color code text in the built in terminal?
2. Is there a more intelligent/clean method of capturing complex settings?  Would an JSON or YAML file be a good method?
3. Is EEPROM support useful?
4. Are there any other transaction types?  Know types are:
   1. Write Addr; Write Reg; Write Data. & Write Addr; Write Reg. Write Addr; Read Data.
   2. Same as above, but with register incrementing on data being multi-byte.
   3. EEPROM Reading/writing pages of data.
   4. Read without register for devices that want to quickly report back a single value. Example of this would be 
      a temperature sensor.  (NOTE: This isn't that common anymore.)
