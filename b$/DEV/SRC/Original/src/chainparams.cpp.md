# chainparams.cpp
Source: https://github.com/bitcoin/bitcoin/blob/master/src/chainparams.cpp

In dieser Datei werden die **Parameter für die verschiedenen BitCoinNetze** gesetzt. 

Die BitCoin App kann in verschiedenen Modi gestartet werden wobei unterschiedliche "Netze" resp. "ChainTypes" generiert und anschliessend im dezentralen Verbund betrieben werden: 

1. **MAIN**: die "scharfe" BitCoin Blockchain.
2. **TESTNET**: Eine TestChain welche genauso gross und langsam wie die "echte" ist. Es werden zwar Blöcke 1:1 generiert und angehängt, haben aber keinen Wert. Diese Chain wird primär für das ausführliche Testen von Softwareupdates verwendet. 
3. **TESTNET4**: ??
4. **SIGNET**: ??
5. **REGTEST**: Mit dieser Chain können auch mal schnell 1000 Blöcke ohne Energie erzeugt werden um das technische Verhalten von Softwareupdates zu testen. 

Jedes dieser Netze kann mit unterschiedlichen Parametern gestartet werden, welche in dieser `chainparams.cpp`-Datei konfiguriert werden. 

---


```plaintext
std::unique_ptr<const CChainParams> CreateChainParams(const ArgsManager& args, const ChainType chain)
{
    switch (chain) {
    case ChainType::MAIN:
        return CChainParams::Main();
    case ChainType::TESTNET:
        return CChainParams::TestNet();
    case ChainType::TESTNET4:
        return CChainParams::TestNet4();
    case ChainType::SIGNET: {
        auto opts = CChainParams::SigNetOptions{};
        ReadSigNetArgs(args, opts);
        return CChainParams::SigNet(opts);
    }
    case ChainType::REGTEST: {
        auto opts = CChainParams::RegTestOptions{};
        ReadRegTestArgs(args, opts);
        return CChainParams::RegTest(opts);
    }
    }
    assert(false);
}
```
