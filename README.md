# PyRandom128
An Upgraded Version of Python's Random Module using SFMT Algorithms in it's place which has 128 bit objects to use as well as compiling features for different Operating Systems.

It will likely be written in CPython because of how optimized the random module itself 
is in order to be faster than it which is my main goal and feature with this new library. 

# Goals With this library 
- Implement a Version of `getrandbytes()` where `_PyLong_FromByteArray` is bypassed so that [CVE-2020-10735](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-10735) cannot be exploited with it which has been known to be a real threat and CPU Killer which has made that function to be rather slow at times...
- Be at least up to par or faster than randommodule.c's implementation whenever it can be done
- Embed SFMT_t's main struct variables into the `Random128Object`
- Have functions be installable like how `winloop` and `uvloop` work where the original random module can still be utilized but with the api calls are replaced with faster ones while newer added api calls can be called from this library
