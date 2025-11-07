Problem Tanımı : Solana ağında cüzdanlara genellikle spam/çöp SPL token’ları gönderilmektedir. Ayrıca kullanıcıların daha önce etkileşime girdiği bazı projeler sonradan likiditesini kaybedip değersiz hale gelen token’lar da tutulabilmektedir.
Çözüm: Solana Junk Token Sweeper çözümünüz ile cüzdanınızdaki değersiz SPL token’ları tespit edip bunları otomatik olarak SOL’a çeviren (swap eden) bir mini uygulama geliştirmektedir.


junk token özellikleri
Etkileşimsiz tespit:
  getTokenAccountsByOwner → mint’leri ve ATA’ları listele
  getSignaturesForAddress(ATA) → ilk tx’i bul 
  getTransaction(firstSig, {maxSupported…}) → “create_associated_token_account” ve ilk transfer instruction’larını parse et
  İşlemde signer’lar, funder ve program id’lerine bak (DEX/aggregator listesiyle eşle)
