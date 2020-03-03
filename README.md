cpuminer-opt-cpupower
---------

*For: CPUchain, Cranepay, Uranium-X and Yenten coin*

**Recommended POOLS:**

http://cpu-pool.com 

InterCoin
``cpuminer.exe -a yespowerinter -o stratum+tcp://cpu-pool.com:63328 -u WALLET_ADDRESS
``

LightBit
``cpuminer.exe -a yespowerlitb -o stratum+tcp://cpu-pool.com:63398 -u WALLET_ADDRESS
``

CPUchain
``cpuminer.exe -a cpupower -o stratum+tcp://cpu-pool.com:63388 -u WALLET_ADDRESS``

Cranepay
``cpuminer.exe -a yespower -o stratum+tcp://cpu-pool.com:63358 -u WALLET_ADDRESS``

Uranium-X
``cpuminer.exe -a yespowerurx -o stratum+tcp://cpu-pool.com:63378 -u WALLET_ADDRESS``

Yenten
``cpuminer.exe -a yespowerr16 -o stratum+tcp://cpu-pool.com:63368 -u WALLET_ADDRESS``

Bellcoin
``cpuminer.exe -a yespower -o stratum+tcp://cpu-pool.com:63338 -u WALLET_ADDRESS``

Microbitcoin
``cpuminer.exe -a power2b -o stratum+tcp://cpu-pool.com:63408 -u WALLET_ADDRESS``

Sugarchain
``cpuminer.exe -a yespowersugar -o stratum+tcp://cpu-pool.com:63418 -u WALLET_ADDRESS``



**Linux and Ubuntu miner** - https://github.com/cpu-pool/cpuminer-opt-cpupower/releases/download/v1.0/Cpuminer-opt-cpupower-linux64.tar.gz

**Download binary miner for windows x64** - https://github.com/cpu-pool/cpuminer-opt-cpupower/releases/

**CPU mining profit calculator** - https://cpu-mining.info/

Compile Ubuntu 16.04, 18.04, 19.04
---------
```
sudo apt-get install -y git
git clone https://github.com/cpu-pool/cpuminer-opt-cpupower.git
cd cpuminer-opt-cpupower
sudo apt-get install -y automake autoconf pkg-config libcurl4-openssl-dev libjansson-dev libssl-dev libgmp-dev make g++
sudo apt-get install -y lib32z1-dev
chmod +x build.sh
./build.sh
```

affinity sample
---------

option: ``` --cpu-affinity=0x555```
and do not forget ```-t 6``` parametrs (6 - number of threads)

                          Good for 16 cores
                          Cores 0,1
                          0x3
                          Cores 0,1,2
                          0x7
                          Cores 0,1,2,3
                          0xF
                          Cores 0,1,2,3,4
                          0x1F
                          Cores 0,1,2,3,4,5
                          0x3F
                          Cores 0,1,2,3,4,5,6
                          0x7F
                          Cores 0,1,2,3,4,5,6,7
                          0xFF
                          Cores 0,1,2,3,4,5,6,7,8
                          0x1FF
                          Cores 0,1,2,3,4,5,6,7,8,9
                          0x3FF
                          Cores 0,1,2,3,4,5,6,7,8,9,10
                          0x7FF
                          Cores 0,1,2,3,4,5,6,7,8,9,10,11
                          0xFFF
                          Cores 0,1,2,3,4,5,6,7,8,9,10,11,12
                          0x1FFF
                          Cores 0,1,2,3,4,5,6,7,8,9,10,11,12,13
                          0x3FFF
                          Cores 0,1,2,3,4,5,6,7,8,9,10,11,12,13,14
                          0x7FFF
                          Cores 0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15
                          0xFFFF
                          
                          Windows affinity, Physical cores
                          Windows enumerates cores differently than linux.
                          Cores 0,2
                          0x5
                          Cores 0,2,4
                          0x15
                          Cores 0,2,4,6
                          0x55
                          Cores 0,2,4,6,8
                          0x155
                          Cores 0,2,4,6,8,10
                          0x555
                          Cores 0,2,4,6,8,10,12
                          0x1555
                          Cores 0,2,4,6,8,10,12,14
                          0x5555
                          Cores 0,2,4,6,8,10,12,14,16
                          0x15555
                          Cores 0,2,4,6,8,10,12,14,16,18
                          0x55555
                          Cores 0,2,4,6,8,10,12,14,16,18,20
                          0x155555
                          Cores 0,2,4,6,8,10,12,14,16,18,20,22
                          0x555555
                          Cores 0,2,4,6,8,10,12,14,16,18,20,22,24
                          0x1555555
                          Cores 0,2,4,6,8,10,12,14,16,18,20,22,24,26
                          0x5555555
                          Cores 0,2,4,6,8,10,12,14,16,18,20,22,24,26,28
                          0x15555555
                          Cores 0,2,4,6,8,10,12,14,16,18,20,22,24,26,28,30
                          0x55555555


sample for CPU 12 threads and 6 cores

```cpuminer.exe -a cpupower -o stratum+tcp://cpu-pool.com:63388 -u WALLET_ADDRESS -t 6 --cpu-affinity=0x555```

--------------------

cpuminer-opt is a fork of cpuminer-multi by TPruvot with optimizations
imported from other miners developped by lucas Jones, djm34, Wolf0, pooler,
Jeff garzik, ig0tik3d, elmad, palmd, and Optiminer, with additional
optimizations by Jay D Dee.

All of the code is believed to be open and free. If anyone has a
claim to any of it post your case in the cpuminer-opt Bitcoin Talk forum
or by email.

Miner programs are often flagged as malware by antivirus programs. This is
a false positive, they are flagged simply because they are cryptocurrency 
miners. The source code is open for anyone to inspect. If you don't trust 
the software, don't use it.

https://bitcointalk.org/index.php?topic=1326803.0

mailto://jayddee246@gmail.com

See file RELEASE_NOTES for change log and compile instructions.

Requirements
------------

1. A x86_64 architecture CPU with a minimum of SSE2 support. This includes
Intel Core2 and newer and AMD equivalents. In order to take advantage of AES_NI
optimizations a CPU with AES_NI is required. This includes Intel Westbridge
and newer and AMD equivalents. Further optimizations are available on some
algoritms for CPUs with AVX and AVX2, Sandybridge and Haswell respectively.

Older CPUs are supported by cpuminer-multi by TPruvot but at reduced
performance.

ARM CPUs are not supported.

2. 64 bit Linux OS. Ubuntu and Fedora based distributions, including Mint and
Centos, are known to work and have all dependencies in their repositories.
Others may work but may require more effort. Older versions such as Centos 6
don't work due to missing features. 
64 bit Windows OS is supported with mingw_w64 and msys or pre-built binaries.

MacOS, OSx and Android are not supported.

3. Stratum pool. Some algos may work wallet mining using getwork or GBT. YMMV.

Supported Algorithms
--------------------

                          allium        Garlicoin
                          anime         Animecoin
                          argon2        Argon2 coin (AR2)
                          argon2d250    argon2d-crds, Credits (CRDS)
                          argon2d500    argon2d-dyn,  Dynamic (DYN)
                          argon2d4096   argon2d-uis, Unitus, (UIS)
                          axiom         Shabal-256 MemoHash
                          bastion
                          blake         Blake-256 (SFR)
                          blakecoin     blake256r8
                          blake2s       Blake-2 S
                          bmw           BMW 256
                          c11           Chaincoin
                          cryptolight   Cryptonight-light
                          cryptonight  
                          cryptonightv7 Monero (XMR)
                          decred
                          deep          Deepcoin (DCN)
                          dmd-gr        Diamond-Groestl
                          drop          Dropcoin
                          fresh         Fresh
                          groestl       Groestl coin
                          heavy         Heavy
                          hmq1725       Espers
                          hodl          Hodlcoin
                          jha           Jackpotcoin
                          keccak        Maxcoin
                          keccakc       Creative coin
                          lbry          LBC, LBRY Credits
                          luffa         Luffa
                          lyra2h        Hppcoin
                          lyra2re       lyra2
                          lyra2rev2     lyra2v2, Vertcoin
                          lyra2z        Zcoin (XZC)
                          lyra2z330     Lyra2 330 rows, Zoin (ZOI)
                          m7m           Magi (XMG)
                          myr-gr        Myriad-Groestl
                          neoscrypt     NeoScrypt(128, 2, 1)
                          nist5         Nist5
                          pentablake    Pentablake
                          phi1612       phi, LUX coin
                          pluck         Pluck:128 (Supcoin)
                          polytimos     Ninja
                          quark         Quark
                          qubit         Qubit
                          scrypt        scrypt(1024, 1, 1) (default)
                          scrypt:N      scrypt(N, 1, 1)
                          scryptjane:nf
                          sha256d       Double SHA-256
                          sha256t       Triple SHA-256, Onecoin (OC)
                          shavite3      Shavite3
                          skein         Skein+Sha (Skeincoin)
                          skein2        Double Skein (Woodcoin)
                          skunk         Signatum (SIGT)
                          timetravel    Machinecoin (MAC)
                          timetravel10  Bitcore
                          tribus        Denarius (DNR)
                          vanilla       blake256r8vnl (VCash)
                          veltor        (VLT)
                          whirlpool
                          whirlpoolx
                          x11           Dash
                          x11evo        Revolvercoin
                          x11gost       sib (SibCoin)
                          x12           Galaxie Cash (GCH)
                          x13           X13
                          x13sm3        hsr (Hshare)
                          x14           X14
                          x15           X15
                          x16r          Ravencoin (RVN)
                          x16s          pigeoncoin (PGN)
                          x17
                          xevan         Bitsend (BSD)
                          yescrypt      Globalboost-Y (BSTY)
                          yescryptr8    BitZeny (ZNY)
                          yescryptr16   Yenten (YTN)
                          yescryptr32   WAVI
                          yespower      Cranepay
                          yespowerr16   Yenten                          
                          cpupower      CPUchain                          
                          yespowerurx   Uranium-X                                                    
                          yespowerlitb  LightBit                                                                              
                          zr5           Ziftr

Errata
------

Neoscrypt crashes on Windows, use legacy version.

AMD CPUs older than Piledriver, including Athlon x2 and Phenom II x4, are not
supported by cpuminer-opt due to an incompatible implementation of SSE2 on
these CPUs. Some algos may crash the miner with an invalid instruction.
Users are recommended to use an unoptimized miner such as cpuminer-multi.

cpuminer-opt does not work mining Decred algo at Nicehash and produces
only "invalid extranonce2 size" rejects.

Benchmark testing does not work for x11evo.

Bugs
----

Users are encouraged to post their bug reports on the Bitcoin Talk
forum at:

https://bitcointalk.org/index.php?topic=1326803.0

All problem reports must be accompanied by a proper definition.
This should include how the problem occurred, the command line and
output from the miner showing the startup and any errors.

Donations
---------

cpuminer-opt has no fees of any kind but donations are accepted.

 BTC: 12tdvfF7KmAsihBXQXynT6E6th2c2pByTT
 ETH: 0x72122edabcae9d3f57eab0729305a425f6fef6d0
 LTC: LdUwoHJnux9r9EKqFWNvAi45kQompHk6e8
 BCH: 1QKYkB6atn4P7RFozyziAXLEnurwnUM1cQ
 BTG: GVUyECtRHeC5D58z9F3nGGfVQndwnsPnHQ

Happy mining!

