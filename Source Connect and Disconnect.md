# How to connect a source

/*
 * ConnectionTest: Test connection to runs and prints results.
 * 	Parameter $1 destination signal.
 * 	Parameter $2 Source signal.
 *
 *	if/else Statement used for logging only. 
 */
subroutine: ConfirmConnection{
    vDestination = $1
    vSource = $2
    
    // Unlocks signal if locked.
      unlock(vDestination) 
    
      // Connects destination to source, returns 0 if successful.
      if(connect(vDestination, vSource) == 0) {
           print("ConfirmConnection " # vDestination # " " # vSource)
      } else {
        print("connection failed")
      }
}


/*
 * ConfirmDisconnect: disconnects destination from source.
 * 	Parameter $1 destination signal.
 * 	Parameter $2 Source signal.
 *
 *	if/else Statement used for logging only. 
 */
subroutine: ConfirmDisconnect{    
    vDestination = $1

      // Unlocks signal if locked.
      unlock(vDestination) 

      // Disconnects destination from source, returns 0 if successful.
      if(disconnect(vDestination) == 0) {
        print("    Disconnected " # vDestination )
     } else {
        print("    Disconnect failed " # vDestination )
    }
} 
