---
title: Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: preparare e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti.'
ms.openlocfilehash: ce158aeaa84e00367b265404fe3d3407606f4759
ms.sourcegitcommit: f3b698379eb663202ce127eeaf6c07328c166556
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/09/2019
ms.locfileid: "38077439"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015

Lo scopo di questo articolo è di specificare le indicazioni necessarie per preparare e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti. Questo processo richiede pianificazione e preparazione estese. Esaminare attentamente tutte le informazioni contenute in questo articolo mentre si imposta il piano per disabilitare TLS 1,0 e 1,1 per l'organizzazione. Tieni presente che esistono molte dipendenze esterne e condizioni di connettività che potrebbero essere interessate dalla disabilitazione di TLS 1.0/1.1, in modo da garantire un'ampia pianificazione e test.

## <a name="in-this-article"></a>In questo articolo

- [Sfondo e ambito](#background)
- [Prerequisiti e processi](#prerequisites-and-process)
- [Scenari di distribuzione avanzati](#advanced-deployment-scenarios)

## <a name="background"></a>Sfondo

I driver principali per la fornitura di TLS 1,0 e 1,1 disabilitano il supporto per Skype for Business Server locale sono i requisiti per gli standard di sicurezza del Consiglio e per l'elaborazione delle informazioni federali. Altre informazioni sui requisiti PCI sono disponibili [qui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft non è in grado di specificare se l'organizzazione deve o meno essere tenuta a rispettare questi o altri requisiti. Devi determinare se è necessario disabilitare TLS 1,0 e/o 1,1 negli ambienti.

Microsoft ha prodotto un white paper su TLS disponibile [qui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e consigliamo anche la lettura in background disponibile in questo [Blog di Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Ambito di supporto

L' *ambito* si riferisce ai limiti di supporto. I mezzi *completamente testati e supportati* supportano completamente e hanno testato la disabilitazione di TLS 1,0 e 1,1 per le versioni di prodotto elencate. *Attualmente in fase di analisi* significa solo questo; Stiamo esaminando attivamente l'opportunità di portare questi prodotti nell'ambito del supporto per disabilitare TLS. *Fuori ambito* significa che queste versioni di prodotto non supportano la disabilitazione di TLS 1,0 o 1,1 e non funzionano, con le eccezioni note.

### <a name="fully-tested-and-supported-servers"></a>Server completamente testati e supportati

- Skype for Business Server 2019 CU1 17.0.2046.123 (giugno 2019) o versioni successive
- Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versione successiva in Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo), 2012 R2 o 2016.
- Sul posto è stato aggiornato Skype for Business Server 2015, con CU9 6.0.9319.548 (maggio 2019) o versioni successive in Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo) o 2012 R2.
- Connettività di Exchange e Outlook Web App con Exchange Server 2010 SP3 RU19 o versioni successive, indicazioni [qui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) con Skype for Business Server 2015 CU6 HF2 o versioni successive (confermare con il fornitore che ha immesso gli aggiornamenti di giuste e che sono stati resi disponibili per l'appliance)
- Survivable Branch Server (SBS) con Skype for Business Server 2015 CU6 HF2 o versioni successive
- **Solo ruolo Edge**di Lync Server 2013, perché il ruolo Edge non ha una dipendenza dal tessuto Windows 1,0.

### <a name="fully-tested-and-supported-clients"></a>Client completamente testati e supportati

- Client desktop di Lync 2013 (Skype for business), MSI e C2R, inclusi i 15.0.5023.1000 di base [o versioni successive](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Client desktop di Skype for business 2016, MSI [16.0.4678.1000 o versioni successive](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluso Basic
- Skype for business 2016 fare clic su Esegui per richiedere gli aggiornamenti di [aprile 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Mirati mensilmente e semestrale, 16\.0\.9126\.2152 o versioni successive
    - Semi-annuale e Deferred Channel, 16\.0\.8431\.2242 o versioni successive
- Skype for business per Mac 16,15 o versioni successive
- Skype for business per iOS e Android 6,19 o versioni successive
- Microsoft teams Rooms (precedentemente noto come Skype room System V2 SRS v2) 4.0.64.0 (2018 dicembre) o versioni successive
- Aggiornamento di Surface hub per Team Edition basato su KB4499162 (2019 maggio, Build 15063,1835 OS) o versioni successive
- Skype Web App 2015 CU6 HF2 o versioni successive (navi con Server)

### <a name="currently-being-investigated"></a>Attualmente in fase di analisi

- Dashboard qualità chiamata (nuova installazione dopo la disattivazione di TLS 1,0, 1,1, vedere di seguito) *
 
### <a name="out-of-scope"></a>Fuori ambito

Eccetto dove indicato, i prodotti seguenti non sono nell'ambito del supporto di Disabilitazione TLS 1.0/1.1 e non funzioneranno in un ambiente in cui TLS 1,0 e 1,1 sono stati disabilitati. Significato: se si usano ancora server o client fuori ambito, è necessario aggiornarli o rimuoverli se è necessario disabilitare TLS 1.0/1.1 in qualsiasi punto della distribuzione locale di Skype for Business Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 o inferiore
- Lync per Mac 2011
- Lync 2013 per dispositivi mobili-iOS, iPad, Android o Windows Phone
- Client di Windows Store "MX" di Lync
- Lync room System (alias SRSv1). LRS ha raggiunto la fine del supporto il 9 ottobre 2018 e non verrà aggiornato per supportare TLS 1,2.
- Tutti i client Lync 2010
- Lync Phone Edition-istruzioni aggiornate [qui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 basato su Survivable Branch Appliance (SBA) o Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Skype for business per Windows Phone

### <a name="exceptions"></a>Eccezioni

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 assume una dipendenza da Windows Fabric versione 1,0.  In fase di progettazione per Lync Server 2013, Windows Fabric 1,0 è stato scelto per la sua convincente e nuova architettura distribuita per consentire la replica, la disponibilità elevata e la tolleranza di errore.  Nel corso del tempo, sia Skype for Business Server che Windows Fabric hanno notevolmente migliorato questa architettura comune con una riprogettazione significativa nelle versioni successive.  Il server Skype for business 2015 corrente usa il tessuto Windows 3,0, ad esempio.

Purtroppo, Windows Fabric 1,0 non **supporta TLS 1,2.  Verrà tuttavia aggiornato Lync Server 2013 per l'utilizzo con TLS 1,2**. Verrà disponibile il prossimo aggiornamento cumulativo per Lync Server 2013.  Stiamo fornendo il supporto di TLS 1,2 per consentire la coesistenza, la migrazione, la Federazione e gli scenari ibridi.

Se è necessaria l'organizzazione per disabilitare TLS 1,0 e 1,1 e attualmente si usa Lync Server 2013, è consigliabile iniziare il processo di pianificazione, con la possibilità di eseguire l'aggiornamento sul posto o la migrazione affiancata (nuovi pool, spostare gli utenti) in Skype for Business Server 2015 o versione successiva.  In alternativa, puoi accelerare la migrazione a Skype for business online.

#### <a name="call-quality-dashboard"></a>Dashboard qualità delle chiamate

Il dashboard di qualità delle chiamate locali ha attualmente una dipendenza da TLS 1,0 durante la nuova installazione (prima volta che si installa in ambienti locali).  Stiamo attualmente esaminando il problema e intendiamo rilasciare una correzione in un prossimo futuro.  Se si prevede di installare Call Quality dashboard e disabilitare anche TLS 1,0, è consigliabile completare prima di tutto l'installazione di Call Quality dashboard e quindi procedere con la disabilitazione di TLS 1,0.

#### <a name="third-party-devices"></a>Dispositivi di terze parti

Nei dispositivi di terze parti, ad esempio telefoni 3PIP, videoconferenze, proxy inverso e servizi di bilanciamento del carico, assicurarsi di convalidare la supportabilità di TLS 1,2, verificare attentamente e contattare il fornitore, se necessario.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerazioni sulla Federazione quando si disabilita TLS 1.0/1.1 in Edge Server

È necessario pianificare attentamente e valutare l'impatto della disabilitazione di TLS 1.0/1.1 nei server perimetrali.  Dopo aver disabilitato TLS 1,0 e 1,1, è possibile che altre organizzazioni non siano più in grado di eseguire la Federazione con l'organizzazione.

Si può scegliere di mantenere TLS 1.0/1.1 abilitato in Edge Server per mantenere la compatibilità con le versioni precedenti di sistemi esterni (SfB 2015, Lync 2013) o versioni precedenti (2010).

Microsoft non è in grado di fornire consigli o raccomandazioni per verificare se la rete Edge (o qualsiasi rete) rientra in standard PCI; Questo deve essere determinato dalla singola società.

Skype for business online è attualmente in grado di TLS 1,2, quindi non è previsto alcun impatto sull'ibrido/Federazione con online.

PIC (connettività per messaggistica istantanea pubblica) a Skype Consumer Service: non prevediamo la disabilitazione di TLS 1.0/1.1 per l'impatto della [connettività Skype](../../deploy/deploy-skype-connectivity.md); I gateway Microsoft PIC sono già in grado di TLS 1,2.

## <a name="prerequisites-and-process"></a>Prerequisiti e processi

Eccetto dove indicato sopra, una volta che i server TLS 1,0 e 1,1 sono disabilitati, i client e i dispositivi non verranno più funzionanti correttamente o a tutti. Ciò significa che è necessario sospendere e attendere le indicazioni aggiornate da Microsoft. Quando si è soddisfatti di soddisfare tutti i requisiti e si ha un piano per affrontare le lacune, procedere.

Ad alto livello, mentre Skype for Business Server 2019 è pronto per la procedura di installazione, Skype for Business Server 2015 richiederà di installare CU9, applicando gli aggiornamenti prerequisiti a .NET e SQL, distribuendo le chiavi del registro di sistema e infine un separato ciclo di aggiornamenti della configurazione del sistema operativo (ad esempio disabilitazione di TLS 1,0 e 1,1 tramite l'importazione di file del registro). È fondamentale completare l'installazione di tutti i prerequisiti, incluso Skype for Business Server 2015 CU6 HF2, prima della disabilitazione di TLS 1,0 e 1,1 in qualsiasi server dell'ambiente. Ogni server Skype for business, inclusi i backend per il ruolo Edge e SQL, richiede gli aggiornamenti. Verificare inoltre che tutti i client supportati (in ambito) siano stati aggiornati alle versioni minime richieste. Non dimenticare di aggiornare anche le workstation di gestione.

Vogliamo seguire l'ordine usuale delle operazioni di "Inside out" per l'aggiornamento dei server Skype for business. Trattare i pool di Director, la chat persistente e i pool di coppie nello stesso modo in cui si farebbe normalmente. L'ordine e i metodi per l'aggiornamento sono coperti [qui](topology.md) e [qui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processo di alto livello

1. Testare tutti i passaggi del Lab prima di configurare i server di produzione.
2. Eseguire il backup e mantenere una copia del registro di sistema esportato su ogni singolo server da aggiornare. Non è possibile condividere i registri tra server, contengono chiavi esclusive basate su computer.
3. Aggiornare tutti i server di Skype for business 2015 in CU9 o versioni successive. Per Skype for Business Server 2019, eseguire l'aggiornamento a CU1 o versioni successive.
4. Installare tutti i prerequisiti per tutti i server.
5. Distribuire le chiavi del registro di sistema prerequisiti.
6. Assicurarsi che tutti i client in ambito vengano aggiornati.
7. Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema.
8. Verificare che i carichi di lavoro funzionino come previsto.
    - Se vengono rilevati problemi, risoluzione dei problemi e Risolvi o
    - Ripristinare il registro di sistema dal passaggio 2 per riattivare TLS 1,0 e 1,1
9. Verificare che venga usato solo TLS 1,2.

### <a name="install-prerequisites-to-all-servers"></a>Installare prerequisiti per tutti i server

È necessario un ampio aggiornamento delle dipendenze prima di iniziare a disabilitare TLS 1,0 e 1,1 a livello di sistema operativo nelle distribuzioni di Skype for Business Server 2015. Di seguito sono riportate le versioni minime in grado di supportare TLS 1,2. Distribuire tutti gli aggiornamenti dei prerequisiti in ogni server Skype for business nell'ambiente prima di iniziare a disabilitare TLS 1,0 e 1,1.

- Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versioni successive
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) o versione successiva con SchUseStrongCrypto abilitato nel registro di sistema (disponibile di seguito)
- SQL deve essere aggiornato in tutti i server e i backend di Skype for business 2015. Aggiornare i backend SQL per il pool di Enterprise Edition prima di tutto, quindi i rispettivi FEs. 
    - SQL Server 2014 SP1 + CU5 ([collegamento](https://support.microsoft.com/help/3130926)) o superiore/sql Server 2012 SP2 + CU16 o superiore/sql Server 2014 RTM + CU12 ([collegamento](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)) o superiore/SQL Server 2014 SP2
     - SQL Server Native Client per SQL Server 2012 ([collegamento](https://www.microsoft.com/download/details.aspx?id=50402))
     - Driver Microsoft ODBC 11 per SQL Server ([collegamento](https://www.microsoft.com/download/details.aspx?id=36434)) o versioni successive
     - Oggetti di gestione condivisi per SQL Server 2014 SP2 ([collegamento](https://www.microsoft.com/download/details.aspx?id=42295))
     - SQLSysClrTypes per SQL Server 2014 SP2 ([collegamento](https://www.microsoft.com/download/details.aspx?id=42295))

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Procedura di base per installare i prerequisiti, in ordine delle operazioni consigliato

1. Installare l'aggiornamento di CU9 per Skype for Business Server in tutti i server. 
    1. Installare l'aggiornamento ai componenti usando l'Updater.
    2. Aggiornare i database in base alle procedure documentate. Per Skype for Business Server 2015, vedere KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Convalidare la funzionalità prodotto nella distribuzione prima di procedere con altre modifiche.
2. Scarica il programma di installazione offline di .NET 4,7. 
    1. Riferimento[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Assicurarsi che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end.
    3. Riferimento[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition):```Stop-CsWindowsService```
    5. Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    6. Eseguire il pacchetto di installazione.
    7. Riavviare il server.
3. Aggiornare SQL Express 2014 in tutti i server. 
    1. Riferimento[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Scaricare SQL 2014 SP2 
        - Riferimento[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copiare il supporto di installazione in una cartella nel server (ad esempio: C:\ 01_2014SqlSp2)
    4. Verificare che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end 
        - Ex (Standard Edition):```Stop-CsWindowsService```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    5. Aprire un prompt dei comandi di amministrazione e aggiornare tutti i componenti e le istanze installati 
        - Esempio: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. Aggiornare SQL Native Client. 
    1. Riferimento: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).
    2. Scarica da[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Verificare che i servizi di 2015 di Skype for Business Server vengano arrestati nel server front-end. 
        - Ex (Standard Edition):```Stop-CsWindowsServices```
        - Ex (Enterprise Edition):```Invoke-CsComputerFailover```
    4. Arrestare l'installazione delle istanze di SQL in uso 
        - Ex```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (solo Standard Edition):```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installare l'aggiornamento.
5. Aggiornare il driver ODBC 11 per SQL Server per includere il supporto per TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Scaricare il [driver ODBC 11 per SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Assicurarsi che i servizi di Skype for Business Server 2015 vengano arrestati nel server front-end.
        - Esempio (Standard Edition):```Stop-CsWindowsService```
        - Esempio (Enterprise Edition):```Invoke-CsComputerFailover```
    3. Installare l'aggiornamento.
6. Distribuire le chiavi del registro di sistema prerequisiti.

### <a name="pre-requisite-registry-keys"></a>Chiavi del registro di sistema pre-richieste

Copiare/incollare il test seguente in blocco note e rinominare TLSPreReq. reg o un nome a scelta, quindi importare:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

Per i backend SQL per i pool Enterprise, i prerequisiti e la Disabilitazione TLS devono essere trattati come qualsiasi aggiornamento di SQL o OS; vedere:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Mentre è possibile combinare sia la procedura per la disabilitazione dell'applicazione prerequisito che quella TLS, consigliamo vivamente di applicare tutti i prerequisiti prima di procedere con la disabilitazione di TLS 1,0 e 1,1 a livello di sistema operativo. L'approccio per la procedura consigliata consiste nel preparare l'ambiente distribuendo tutti i prerequisiti, convalidando che tutti i carichi di lavoro funzionino correttamente e come previsto e quindi procedendo con la Disabilitazione TLS 1.0/1.1 in un secondo momento.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema

Prima di procedere con i passaggi successivi, verificare di *aver completato tutti i prerequisiti e i server Skype for business aggiornati*.

Copiare il testo seguente in un file di blocco note e rinominarlo **TLSDisable. reg**:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

Importare il file con estensione reg in ogni server che si vuole disabilitare TLS 1,0 e 1,1. Riavviare il server. Dopo che i servizi sono tornati online, passare al server successivo. L'approccio per i pool Enterprise Edition è lo stesso che si può fare per qualsiasi aggiornamento del sistema operativo.

Potresti aver notato che stiamo facendo molto di più che disabilitare solo TLS 1,0 e 1,1 qui. Stiamo supportando il riordino di Cipher Suite (come illustrato sopra) e la disattivazione di alcuni cifrari deboli meno recenti. Questa è la prima volta che abbiamo ufficialmente supportato queste modifiche all'API SCHANNEL e Crypto in Skype for Business Server ed è importante notare che queste modifiche sono le uniche supportate e testate in questo momento. Potremmo prendere in considerazione altre configurazioni in futuro, ma per il momento, non modificare il file di importazione del registro di sistema nell'implementazione.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Verificare che i carichi di lavoro funzionino come previsto

Dopo aver disabilitato TLS 1,0 e 1,1 nell'ambiente, verificare che tutti i carichi di lavoro principali funzionino come previsto, ad esempio messaggistica istantanea & presenza, chiamate P2P, VoIP aziendale e così via.

**Convalidare solo TLS 1,2 viene usato**

Fai in modo che il tuo team di sicurezza esegua un nuovo controllo del traffico Skype for business per assicurarti che i protocolli meno recenti TLS 1,0 e 1,1 non siano più in uso.

In alternativa, è possibile usare Internet Explorer per testare le connessioni TLS ai servizi Web da Skype for Business Server 2015 dopo la disattivazione di TLS 1,0 e TLS 1,1.

1. Avviare Internet Explorer.
2. Selezionare **strumenti** > **Internet Options**.
3. Selezionare la scheda **Avanzate** .
4. In **Impostazioni**scorrere fino alla fine.
5. Verificare che TLS 1,0, TLS 1,1 e TLS 1,2 siano abilitati.
6. Esplorare l'URL del servizio Web interno del pool di SfB 2015 (deve connettersi correttamente).
7. Tornare in Internet Explorer e disabilitare l'opzione per l' **uso solo di TLS 1,2** .
8. Esplorare di nuovo l'URL del servizio Web interno del pool di SfB 2015 (non riesce a connettersi).

![Opzioni Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Scenari di distribuzione avanzati

Poiché sono necessari alcuni prerequisiti di dipendenza per supportare TLS 1,2 in Skype for business ser 2015, l'installazione da supporto RTM non riesce in qualsiasi sistema in cui TLS 1,0 e 1,1 sono stati disabilitati.

**Distribuzione di nuovi server Standard Edition o pool di Enterprise Edition dopo la disattivazione di TLS 1,0 e 1,1 nell'ambiente.**

**Opzione 1:** Usare [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Tieni presente che stiamo aggiornando SmartSetup per adattare i file binari SQL aggiornati in un futuro CU e aggiorniamo questo articolo in futuro.

**Opzione 2:** Pre-installare istanze locali di SQL (RTCLOCAL e LYNCLOCAL)

1. Scaricare e copiare SQL Express 2014 SP2 (SQLEXPR_x64. exe) nella cartella locale in FE. Supponiamo che il percorso della cartella <SQL_FOLDER_PATH>.
2. Avviare PowerShell o prompt dei comandi e passare a <SQL_FOLDER_PATH>.
3. Creare l'istanza di SQL RTCLOCAL eseguendo il comando seguente. Attendere che SQLEXPR_x64. exe finisca prima di procedere:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati
1. Creare l'istanza di SQL LYNCLOCAL eseguendo il comando seguente. Attendere che SQLEXPR_x64. exe finisca prima di procedere con il passaggio successivo:

    SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic
1. Eseguire la configurazione RTM di Skype for Business Server 2015.
2. Seguire i passaggi rimanenti della sezione Prerequisiti precedente.

**Opzione 3:** È anche possibile sostituire manualmente i file binari in una directory multimediale di installazione locale come indicato di seguito:

1. [Installare prerequisiti per Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Installare .NET 4,7: 
      - **Nota:** Per la prima volta è stato introdotto il supporto per .NET 4,7 in Skype for Business Server 2015 CU5 (6.0.9319.281). Pertanto, nei passaggi successivi di seguito verranno aggiornati i componenti principali prima dell'installazione principale.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167. 
      - Riferimento: [software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiare file/cartelle ISO: 
    - Con l'ISO di Skype for Business Server 2015 allegato, aprire la directory radice dell'unità in cui è collegata (es: D:\) in Esplora file.
    - Copiare tutte le cartelle e i file in una cartella in un disco locale (es: C:\SkypeForBusiness2015ISO).
    - **Nota:** Prima di installare i componenti, sarà necessario aggiornare alcuni file per il supporto di TLS 1,2.
4. Sostituire i pacchetti MSI/EXE: 
    - Sostituire i pacchetti MSI e EXE esistenti nella cartella/Setup/amd64/del supporto di installazione nel computer locale.
    - SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167 
        - Rinominare in SQLEXPR_x64 nel computer locale e sostituire il file esistente nella cartella Setup/amd64/del supporto di installazione.
    - SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402 
        - **Nota:** Rinominare questo elemento, se necessario, in sqlncli. msi e quindi sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.
    - Oggetti di gestione SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Nota:** Il Feature Pack includerà molti elementi che possono essere scaricati. Selezionare questa pagina per scaricare solo SharedManagementObjects. msi.
        - **Nota:** Sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.
    - Tipi CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164 
        - **Nota:** Il Feature Pack includerà molti elementi che possono essere scaricati. Selezionare per scaricare solo CQLSysClrTypes. msi
        - **Nota**: sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.
5. Installare componenti principali: 
    - Eseguire Setup. exe dalla cartella Setup/amd64/del supporto di installazione. Seguire le istruzioni per installare i componenti principali
    - Chiudere i componenti principali.
6. Aggiornare i componenti principali: 
    - Scaricare il programma di installazione di Skype for Business Update.
    - Eseguire il programma di installazione per aggiornare i componenti principali e installare i contatori delle prestazioni.
    - **Nota:** A partire dal rilascio di CU6HF2, la caratteristica di aggiornamento automatico attualmente viene installata solo fino a CU6. Di conseguenza, l'Updater deve essere eseguito separatamente per aggiornare i componenti principali in 6.0.9319.516.
    - Riferimentohttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015
7. Installare strumenti amministrativi (facoltativo): 
    - In questo modo verranno installati Microsoft SQL Server 2012 Native client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types per SQL Server 2014 (x64) con i file aggiornati. Inoltre, il generatore di topologie e il pannello di controllo di Skype for Business Server 2015 saranno disponibili nel computer locale.
8. Installare lo Store di configurazione locale (passaggio 1): 
     - Aprire la distribuzione guidata, fare clic su Installa o Aggiorna Skype for Business Server System, quindi fare clic su **Esegui** al passaggio 1: installare l'archivio configurazione locale.
     - Fare clic su **Avanti** nella finestra di dialogo **Installa archivio configurazione locale** .
     ![Finestra di dialogo Installa archivio configurazione locale](../../media/local-configuration-store.png)
     - Esaminare i risultati e verificare che lo stato dell'attività sia stato completato. Esaminare il file di log risultante facendo clic su **Visualizza log**.
     ![Lo stato delle attività viene visualizzato come completato](../../media/local-configuration-task-completed.png)
     - Fare clic su **fine**.
9. Configurare o rimuovere componenti di Skype for Business Server (passaggio 2):
    - Aprire la distribuzione guidata, fare clic su **Installa o Aggiorna Skype for Business Server System**, quindi fare clic su **Esegui** al passaggio 2: configurare o rimuovere componenti di Skype for Business Server
    - Fare clic su **Avanti** nella finestra di dialogo Configura componenti di Skype for Business Server.
    ![finestra Configura componenti di Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Rivedere il log usando il log della visualizzazione e verificare che il programma di installazione sia stato completato senza problemi. 
    - Fare clic su **fine**.
10. Procedere con l'installazione e la configurazione aggiuntive necessarie (è possibile riprendere le normali procedure di installazione a questo punto).
