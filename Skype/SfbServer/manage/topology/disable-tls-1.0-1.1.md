---
title: Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Sintesi: preparare e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti.'
ms.openlocfilehash: 06ebc3f5821e8daa1c80633b25140a852f72097d
ms.sourcegitcommit: 4143ce9bd62e67ba09f89cedadfd65803bda5361
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734294"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a>Disabilitare TLS 1.0/1.1 in Skype for Business Server 2015

Lo scopo di questo articolo è fornire le informazioni necessarie per prepararsi e implementare la disabilitazione di TLS 1,0 e 1,1 negli ambienti. Questo processo richiede una pianificazione e una preparazione estese. Leggere attentamente tutte le informazioni contenute in questo articolo quando si pianifica la disabilitazione di TLS 1,0 e 1,1 per la propria organizzazione. Si noti che sono presenti molte dipendenze esterne e condizioni di connettività che possono essere influenzate dalla disattivazione di TLS 1.0/1.1, pertanto è garantita una pianificazione e un testing estensivi.

## <a name="in-this-article"></a>In questo articolo

- [Sfondo e ambito](#background)
- [Prerequisiti e processi](#prerequisites-and-process)
- [Scenari di distribuzione avanzata](#advanced-deployment-scenarios)

## <a name="background"></a>Sfondo

I driver principali per la fornitura di TLS 1,0 e 1,1 disabilitano il supporto per Skype for Business Server in locale sono i requisiti per gli standard di sicurezza di Payment Card Industry (PCI) e Federal Information Processing Standards. Per ulteriori informazioni sui requisiti PCI è possibile trovare [qui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).  Microsoft non è in grado di fornire indicazioni sulla necessità o meno dell'organizzazione di aderire a questi o ad altri requisiti. È necessario determinare se è necessario disabilitare TLS 1,0 e/o 1,1 negli ambienti.

Microsoft ha prodotto un white paper su TLS disponibile [qui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), ed è consigliabile anche la lettura in background disponibile in questo [Blog di Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).

## <a name="supportability-scope"></a>Ambito di supporto

L' *ambito* si riferisce ai limiti di supporto. *Pienamente testato e supportato* significa che sono stati completamente supportati e hanno testato la disabilitazione di TLS 1,0 e 1,1 per le versioni di prodotto elencate. *Attualmente in fase di indagine* significa solo che; Stiamo attivamente studiando la possibilità di introdurre questi prodotti nell'ambito del supporto per la Disabilitazione TLS. *Fuori campo* significa che queste versioni di prodotto non supportano la disabilitazione di TLS 1,0 o 1,1 e non funzionano, con le eccezioni note.

### <a name="fully-tested-and-supported-servers"></a>Server completamente testati e supportati

- Skype for Business Server 2019 CU1 17.0.2046.123 (giugno 2019) o superiore
- Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o versioni successive su Windows Server 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo), 2012 R2 o 2016.
- Aggiornamento sul posto di Skype for Business Server 2015, con CU9 6.0.9319.548 (maggio 2019) o versioni successive su Windows Server 2008 R2, 2012 (con KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) o aggiornamento sostitutivo) oppure 2012 R2.
- Connettività di Exchange e Outlook Web App con Exchange Server 2010 SP3 RU19 o versione successiva, linee guida [qui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- Survivable Branch Appliance (SBA) con Skype for Business Server 2015 CU6 HF2 o versione successiva (verificare con il fornitore che hanno inserito gli aggiornamenti corretti e che sono stati resi disponibili per il dispositivo)
- Survivable Branch Server (SBS) con Skype for Business Server 2015 CU6 HF2 o versione successiva
- **Solo ruolo** di Lync Server 2013 Edge, perché il ruolo Edge non ha una dipendenza da Windows Fabric 1,0.

### <a name="fully-tested-and-supported-clients"></a>Client completamente testati e supportati

- Client desktop Lync 2013 (Skype for business), MSI e C2R, tra cui [15.0.5023.1000 di base o versione successiva](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)
- Client desktop Skype for business 2016, MSI [16.0.4678.1000 o versione successiva](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluso Basic
- Skype for business 2016 fare clic su Esegui per richiedere gli aggiornamenti di [aprile 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) : 
    - Mensili e Semi-Annual mirati, 16 \. 0 \. 9126 \. 2152 o versioni successive
    - Semi-Annual e Deferred Channel, 16 \. 0 \. 8431 \. 2242 o versioni successive
- Skype for business su Mac 16,15 o versione successiva
- Skype for business per iOS e Android 6,19 o versione successiva
- Microsoft teams Rooms (precedentemente noto come Skype room System V2 SRS v2) 4.0.64.0 (2018 dicembre) o versioni successive
- Aggiornamento dell'hub di superficie per Team Edition basato su KB4499162 (maggio 2019, Build 15063,1835 OS) o superiore
- Skype Web App 2015 CU6 HF2 o versioni successive (navi con Server)

### <a name="currently-being-investigated"></a>Attualmente in fase di analisi

- Call Quality Dashboard (nuova installazione dopo che TLS 1,0, 1,1 sono stati disabilitati, vedere di seguito) *
 
### <a name="out-of-scope"></a>Esclusioni

Eccetto dove indicato, i prodotti seguenti non sono nell'ambito del supporto per la disabilitazione di TLS 1.0/1.1 e non funzioneranno in un ambiente in cui TLS 1,0 e 1,1 sono stati disabilitati. Cosa significa: se si utilizzano ancora server o client fuori ambito, è necessario aggiornarli o rimuoverli se è necessario disabilitare TLS 1.0/1.1 in qualsiasi punto della distribuzione locale di Skype for Business Server.

- Lync Server 2013
- Lync Server 2010
- Windows Server 2008 o inferiore
- Lync per Mac 2011
- Lync 2013 per dispositivi mobili-iOS, iPad, Android o Windows Phone
- Lync "MX" client Windows Store
- Lync room System (aka SRSv1). LRS ha raggiunto la fine del supporto il 9 ottobre 2018 e non verrà aggiornato per supportare TLS 1,2.
- Tutti i client Lync 2010
- Lync Phone Edition-informazioni aggiornate [qui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).
- 2013 basato Survivable Branch Appliance (SBA) o Survivable Branch Server (SBS)
- Cloud Connector Edition (CCE)
- Skype for business per Windows Phone

### <a name="exceptions"></a>Eccezioni

#### <a name="lync-server-2013"></a>Lync Server 2013

Lync Server 2013 assume una dipendenza da Windows Fabric versione 1,0.  In fase di progettazione per Lync Server 2013, Windows Fabric 1,0 è stato scelto per la nuova architettura convincente e distribuita per fornire la replica, la disponibilità elevata e la tolleranza di errore.  Nel corso del tempo, sia Skype for Business Server che Windows Fabric hanno notevolmente migliorato questa architettura comune con una riprogettazione significativa nelle versioni successive.  L'attuale server Skype for business 2015 utilizza Windows Fabric 3,0, ad esempio.

Purtroppo, Windows Fabric 1,0 non **supporta TLS 1,2.  Tuttavia, verrà aggiornato Lync Server 2013 per l'utilizzo con TLS 1,2**. Questo verrà nel prossimo aggiornamento cumulativo per Lync Server 2013.  Il supporto di TLS 1,2 viene fornito per consentire la coesistenza, la migrazione, la Federazione e gli scenari ibridi.

Se l'organizzazione è necessaria per disabilitare TLS 1,0 e 1,1 e attualmente si utilizza Lync Server 2013, è consigliabile iniziare il processo di pianificazione, con la possibilità di eseguire l'aggiornamento sul posto o la migrazione affiancata (nuovi pool, spostare gli utenti) su Skype for Business Server 2015 o versione successiva.  In alternativa, si consiglia di accelerare la migrazione a Skype for business online.

#### <a name="call-quality-dashboard"></a>Dashboard Qualità della chiamata

Il dashboard per la qualità delle chiamate in locale è attualmente dipendente da TLS 1,0 durante la nuova installazione (prima installazione negli ambienti locali).  Attualmente stiamo indagando su questo problema e intendiamo rilasciarne una soluzione nel prossimo futuro.  Se si prevede di installare CQD e anche di disabilitare TLS 1,0, è consigliabile completare prima l'installazione di CQD e quindi procedere con la disabilitazione di TLS 1,0.

#### <a name="skype-for-business-sdn-manager"></a>Gestione di Skype for business SDN

Skype for business SDN Manager using SQL a database ha una dipendenza da TLS 1,0 durante la nuova installazione. Se si prevede di installare Skype for business SDN Manager tramite database SQL a e di disabilitare TLS 1,0, è consigliabile completare prima Skype for business SDN Manager e quindi procedere con la disabilitazione di TLS 1,0. Nel caso in cui TLS 1,0 fosse disabilitato prima dell'installazione, è necessario abilitare temporaneamente TLS 1,0 nel server back-end di SQL Server che verrà utilizzato per ospitare il database SQL di Skype for business SDN Manager.

#### <a name="third-party-devices"></a>Dispositivi di terze parti

Nei dispositivi di terze parti, ad esempio i telefoni 3PIP, le videoconferenze, i proxy inversi e i servizi di bilanciamento del carico, accertarsi di convalidare la supportabilità di TLS 1,2, testare attentamente e contattare il fornitore, se necessario.

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a>Considerazioni sulla Federazione per la disabilitazione di TLS 1.0/1.1 nei server perimetrali

È necessario pianificare attentamente e valutare l'impatto della disabilitazione di TLS 1.0/1.1 nei server perimetrali.  Dopo la disabilitazione di TLS 1,0 e 1,1, è possibile che altre organizzazioni non siano più in grado di eseguire la Federazione con l'organizzazione.

È possibile scegliere di mantenere TLS 1.0/1.1 abilitato sui server perimetrali per mantenere la compatibilità con le versioni precedenti dei sistemi esterni (questo 2015, Lync 2013) o versioni precedenti (2010).

Microsoft non è in grado di fornire consigli o suggerimenti su se la rete perimetrale (o qualsiasi rete) rientra in standard PCI; che deve essere determinata dalla singola società.

Skype for business online è in grado di TLS 1,2 oggi, quindi non è previsto alcun impatto su ibrido/Federazione con online.

PIC (connettività di messaggistica istantanea pubblica) per Skype Consumer Service: non si prevede che la disabilitazione di TLS 1.0/1.1 influenzi la [connettività Skype](../../deploy/deploy-skype-connectivity.md); I gateway Microsoft PIC sono già in grado di disporre di TLS 1,2.

## <a name="prerequisites-and-process"></a>Prerequisiti e processi

Eccetto se sopra indicato, una volta che i server TLS 1,0 e 1,1 sono disabilitati, i client e i dispositivi possono funzionare più a lungo. Ciò può significare che è necessario sospendere e attendere l'aggiornamento delle indicazioni di Microsoft. Una volta che si è soddisfatti di soddisfare tutti i requisiti e di avere un piano per risolvere gli spazi vuoti, procedere.

Ad alto livello, mentre Skype for Business Server 2019 è pronto per la procedura di installazione, Skype for Business Server 2015 richiede l'installazione di CU9, l'applicazione di aggiornamenti prerequisiti a .NET e SQL, la distribuzione delle chiavi del registro di sistema prerequisite e infine un round separato di aggiornamenti di configurazione dei sistemi operativi (ovvero la disabilitazione di TLS 1,0 e 1,1 tramite importazione file di registro È estremamente importante completare l'installazione di tutti i prerequisiti, tra cui Skype for Business Server 2015 CU6 HF2, prima di disabilitare TLS 1,0 e 1,1 su qualsiasi server dell'ambiente. Ogni server Skype for business, inclusi i ruoli Edge e SQL, richiede gli aggiornamenti. Verificare inoltre che tutti i client supportati (nell'ambito) siano stati aggiornati alle versioni minime necessarie. Non dimenticare di aggiornare anche le workstation di gestione.

Per l'aggiornamento dei server Skype for business, è necessario seguire l'ordine usuale di operazioni "all'interno". Trattare i pool di server Director, la chat persistente e i pool associati nello stesso modo in cui si farebbe normalmente. L'ordine e i metodi per l'aggiornamento sono descritti [qui](topology.md) e [qui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

### <a name="high-level-process"></a>Processo di alto livello

1. Testare tutti i passaggi del Lab prima di configurare i server di produzione.
2. Eseguire il backup e la conservazione di una copia del registro di sistema esportato su ogni singolo server da aggiornare. Non è possibile condividere i registri tra i server; contengono chiavi esclusive basate su computer.
3. Aggiornare tutti i server Skype for business 2015 a CU9 o versione successiva. Per Skype for Business Server 2019, eseguire l'aggiornamento a CU1 o versione successiva.
4. Installare tutti i prerequisiti in tutti i server.
5. Distribuire le chiavi del registro di sistema prerequisite.
6. Verificare che tutti i client nell'ambito vengano aggiornati.
7. Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema.
8. Verificare che i carichi di lavoro funzionino come previsto.
    - Se vengono rilevati problemi, risolverli o risolvere il problema, oppure
    - Ripristinare il registro di sistema dal passaggio 2 per riattivare TLS 1,0 e 1,1
9. Verificare che sia in uso solo TLS 1,2.

### <a name="install-prerequisites-to-all-servers"></a>Installare i prerequisiti in tutti i server

È necessario un aggiornamento estensivo delle dipendenze prima di iniziare a disabilitare TLS 1,0 e 1,1 a livello del sistema operativo nelle distribuzioni di Skype for Business Server 2015. Di seguito sono riportate le versioni minime che supportano TLS 1,2. Distribuire tutti gli aggiornamenti prerequisiti in ogni server Skype for business nel proprio ambiente prima di iniziare la disabilitazione di TLS 1,0 e 1,1.

- Skype for Business Server 2015 CU9 6.0.9319.548 (maggio 2019) o superiore
- [.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) o versione successiva con schusestrongcrypto consente abilitato nel registro di sistema (disponibile di seguito)
- SQL deve essere aggiornato su tutti i server e i backend di Skype for business 2015. Aggiornare le backends SQL del pool Enterprise Edition in primo luogo, quindi le rispettive FEs. 
    - [SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)o versione successiva/sql Server 2012 SP2 + CU16 o versione successiva/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)o superiore/SQL Server 2014 SP2
     - [SQL Server Native Client per SQL Server 2012](https://www.microsoft.com/download/details.aspx?id=50402)
     - [Microsoft ODBC driver 11 per SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)o versione successiva
     - [Oggetti di gestione condivisi per SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=53164)
     - [SQLSysClrTypes per SQL Server 2014 SP2](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a>Passaggi di base per l'installazione dei prerequisiti, in ordine di operazioni consigliato

1. Installare l'aggiornamento di CU9 per Skype for Business Server su tutti i server. 
    1. Installare l'aggiornamento ai componenti utilizzando l'Updater.
    2. Aggiornare i database in base alle procedure documentate. Per Skype for Business Server 2015, vedere KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).
    3. Convalidare la funzionalità del prodotto nella distribuzione prima di procedere con altre modifiche.
2. Scaricare il programma di installazione di .NET 4,7 offline. 
    1. Riferimento [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)
    2. Assicurarsi che i servizi di Skype for Business Server 2015 siano stati arrestati nel front end server.
    3. Riferimento [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)
    4. Ex (Standard Edition): ```Stop-CsWindowsService```
    5. Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    6. Eseguire il pacchetto del programma di installazione.
    7. Riavviare il server.
3. Aggiornare SQL Express 2014 su tutti i server. 
    1. Riferimento [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)
    2. Scaricare SQL 2014 SP2 
        - Riferimento [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)
    3. Copiare il supporto di installazione in una cartella sul server (ad esempio, C:\ 01_2014SqlSp2)
    4. Verificare che i servizi di Skype for Business Server 2015 siano stati arrestati nel front end server 
        - Ex (Standard Edition): ```Stop-CsWindowsService```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    5. Aprire un prompt dei comandi di amministratore e aggiornare tutti i componenti e le istanze installati 
        - Esempio: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances
4. Aggiornare SQL Native Client. 
    1. Riferimento: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .
    2. Scaricare da [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)
    3. Verificare che i servizi di Skype for Business Server 2015 siano stati arrestati nel front end server. 
        - Ex (Standard Edition): ```Stop-CsWindowsServices```
        - Ex (Enterprise Edition): ```Invoke-CsComputerFailover```
    4. Interrompere l'esecuzione delle istanze di SQL installate 
        - Ex ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```
        - Ex ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```
        - Ex (solo Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```
    5. Installare l'aggiornamento.
5. Aggiornare il driver ODBC 11 per SQL Server in modo da includere il supporto per TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).
    1. Scaricare [ODBC driver 11 for SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).
    2. Assicurarsi che i servizi di Skype for Business Server 2015 siano stati arrestati nel front end server.
        - Esempio (Standard Edition): ```Stop-CsWindowsService```
        - Esempio (Enterprise Edition): ```Invoke-CsComputerFailover```
    3. Installare l'aggiornamento.
6. Distribuire le chiavi del registro di sistema prerequisite.

### <a name="pre-requisite-registry-keys"></a>Chiavi del registro di sistema prerequisite

Copia/incolla il test seguente nel blocco note e Rinomina TLSPreReq. reg o un nome di vostra scelta, quindi importa:

```console
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

Per i back-end SQL per i pool Enterprise Edition, i prerequisiti e la disabilitazione di TLS devono essere considerati come qualsiasi aggiornamento di SQL o OS; fare riferimento a: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)

Sebbene sia possibile combinare entrambi i passaggi di disabilitazione dell'applicazione prerequisito e TLS, è consigliabile applicare tutti i prerequisiti prima di procedere con la disabilitazione di TLS 1,0 e 1,1 a livello del sistema operativo. L'approccio per la procedura consigliata consiste nel preparare l'ambiente distribuendo tutti i prerequisiti, convalidando che tutti i carichi di lavoro funzionino correttamente e come previsto e quindi procedendo con la disabilitazione di TLS 1.0/1.1 in un secondo momento.

### <a name="disable-tls-10-and-11-via-registry-import"></a>Disabilitare TLS 1,0 e 1,1 tramite l'importazione del registro di sistema

Prima di procedere con i passaggi successivi, accertarsi di *aver completato tutti i prerequisiti e di aver aggiornato i server Skype for business*.

Copiare il testo seguente in un file del blocco note e rinominarlo **TLSDisable. reg**:

```console
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

Importare il file con estensione reg in ogni server che si desidera disabilitare TLS 1,0 e 1,1. Riavviare il server. Dopo che i servizi sono ritornati online, passare al server successivo. L'approccio per i pool Enterprise Edition è lo stesso necessario per qualsiasi aggiornamento del sistema operativo.

È possibile che si noti che non è sufficiente disabilitare TLS 1,0 e 1,1 qui. Noi sosteniamo il riordino della famiglia di crittografia (come mostrato sopra) e la disabilitazione di alcuni vecchi cifrari deboli. Questa è la prima volta che sono state supportate ufficialmente queste modifiche a SCHANNEL e Crypto API su Skype for Business Server ed è importante tenere presente che queste modifiche sono le uniche che supportano e che sono state testate in questo momento. È possibile prendere in considerazione altre configurazioni in futuro, ma per il momento, non modificare il file di importazione del registro di sistema nell'implementazione.

### <a name="validate-that-workloads-are-functioning-as-expected"></a>Convalidare il funzionamento dei carichi di lavoro come previsto

Una volta che TLS 1,0 e 1,1 sono stati disabilitati nell'ambiente, verificare che tutti i carichi di lavoro principali funzionino come previsto, ad esempio la presenza di & di messaggistica istantanea, le chiamate P2P, VoIP aziendale e così via.

**Convalidare solo TLS 1,2 utilizzato**

Fare in modo che il team di sicurezza esegua un nuovo controllo del traffico di Skype for business per assicurarsi che i protocolli meno recenti TLS 1,0 e 1,1 non siano più in uso.

In alternativa, è possibile utilizzare Internet Explorer per testare le connessioni TLS ai servizi Web da Skype for Business Server 2015 dopo che TLS 1,0 e TLS 1,1 sono stati disabilitati.

1. Avviare Internet Explorer.
2. Selezionare **strumenti**  >  **Internet Options**.
3. Selezionare la scheda **Avanzate** .
4. In **Impostazioni**, scorrere fino alla fine.
5. Verificare che TLS 1,0, TLS 1,1 e TLS 1,2 siano abilitati.
6. Passare all'URL del servizio Web interno del pool di questo 2015 (è necessario connettersi correttamente).
7. Tornare in Internet Explorer e disabilitare l'opzione per l' **utilizzo solo di TLS 1,2** .
8. Consultare di nuovo l'URL del servizio Web interno del pool di questo 2015 (se la connessione non riesce).

![Opzioni Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a>Scenari di distribuzione avanzata

Poiché alcuni prerequisiti di dipendenza sono necessari per supportare TLS 1,2 in Skype for Business Server 2015, l'installazione da supporto RTM avrà esito negativo su qualsiasi sistema in cui TLS 1,0 e 1,1 sono stati disabilitati.

**Distribuzione di nuovi server Standard Edition o pool Enterprise Edition dopo che TLS 1,0 e 1,1 sono stati disabilitati nell'ambiente in uso.**

**Opzione 1:** Utilizzare [SmartSetup](../../deploy/install/install-skype-for-business-server.md). Si noti che si sta aggiornando SmartSetup per ospitare i file binari SQL aggiornati in un futuro CU e questo articolo verrà aggiornato in futuro.

**Opzione 2:** Preinstallare le istanze di SQL locali (RTCLOCAL e LYNCLOCAL)

1. Scaricare e copiare SQL Express 2014 SP2 (SQLEXPR_x64.exe) nella cartella locale su FE. Si supponga che il percorso della cartella <SQL_FOLDER_PATH>.
2. Avviare PowerShell o prompt di comandi e passare a <SQL_FOLDER_PATH>.
3. Creare l'istanza SQL di RTCLOCAL eseguendo il comando riportato di seguito. Attendere fino a quando non viene completata SQLEXPR_x64.exe prima di procedere:

    SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automati
1. Creare l'istanza SQL di LYNCLOCAL eseguendo il comando riportato di seguito. Attendere fino al termine della SQLEXPR_x64.exe prima di procedere con il passaggio successivo:

    SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = install/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic
1. Eseguire il programma di installazione di Skype for Business Server 2015 RTM.
2. Seguire i passaggi rimanenti dalla sezione Prerequisites precedente.

**Opzione 3:** È inoltre possibile sostituire manualmente i file binari in una directory media di installazione locale, come indicato di seguito:

1. [Installare i prerequisiti per Skype for Business Server](../../deploy/install/install-prerequisites.md)  
2. Installare .NET 4,7: 
      - **Nota:** Per la prima volta è stato introdotto il supporto per .NET 4,7 in Skype for Business Server 2015 CU5 (6.0.9319.281). Pertanto, nei passaggi successivi di seguito verranno aggiornati i componenti di base prima dell'installazione principale.
      - Download: https://www.microsoft.com/download/details.aspx?id=55167 . 
      - Riferimento: [software che deve essere installato prima di una distribuzione di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)
3. Copiare i file/cartelle ISO: 
    - Con Skype for Business Server 2015 ISO allegato, aprire la directory radice dell'unità in cui è collegato come (es: D: \) in Esplora file.
    - Copiare tutte le cartelle e i file in una cartella su un disco locale (ad esempio, C:\SkypeForBusiness2015ISO).
    - **Nota:** Prima di installare i componenti, alcuni file dovranno essere aggiornati per il supporto di TLS 1,2.
4. Sostituire i pacchetti MSI/EXE: 
    - Sostituire i pacchetti MSI e EXE esistenti nella cartella/Setup/amd64/del supporto di installazione nel computer locale.
    - SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167 
        - Rinominare SQLEXPR_x64 nel computer locale e sostituire il file esistente nella cartella Setup/amd64/del supporto di installazione.
    - SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402 
        - **Nota:** Rinominarla se necessario per sqlncli.msi, quindi sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.
    - Oggetti di gestione SQL: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** Il Feature Pack avrà un sacco di elementi che possono essere scaricati. Selezionare per scaricare solo SharedManagementObjects.msi.
        - **Nota:** Sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.
    - Tipi CLR SQL: https://www.microsoft.com/download/details.aspx?id=53164 
        - **Nota:** Il Feature Pack avrà un sacco di elementi che possono essere scaricati. Seleziona per scaricare solo CQLSysClrTypes.msi
        - **Nota**: sostituire il file esistente presente nella cartella Setup/amd64/del supporto di installazione.
5. Installare i componenti di base: 
    - Eseguire Setup.exe dalla cartella Setup/amd64/del supporto di installazione. Seguire le istruzioni per installare i componenti di base
    - Chiudere i componenti di base.
6. Aggiornare i componenti di base: 
    - Scaricare il programma di installazione degli aggiornamenti di Skype for business.
    - Eseguire il programma di installazione per aggiornare i componenti di base e installare i contatori delle prestazioni.
    - **Nota:** Dopo la versione di CU6HF2, la caratteristica di aggiornamento automatico verrà installata solo fino a CU6. Pertanto, l'Updater deve essere eseguito separatamente per aggiornare i componenti di base a 6.0.9319.516.
    - Riferimento https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015
7. Installare gli strumenti di amministrazione (facoltativo): 
    - In questo modo, verranno installati Microsoft SQL Server 2012 Native client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types for SQL Server 2014 (x64) utilizzando i file aggiornati. Inoltre, il generatore di topologie e il pannello di controllo di Skype for Business Server 2015 saranno disponibili nel computer locale.
8. Installare l'archivio di configurazione locale (passaggio 1): 
     - Aprire la distribuzione guidata, fare clic su Installa o aggiorna il sistema di Skype for Business Server, quindi fare clic su **Esegui** al passaggio 1: installazione dell'archivio di configurazione locale.
     - Fare clic su **Avanti** nella finestra di dialogo **Installa archivio di configurazione locale** .
     ![Finestra di dialogo Installa archivio di configurazione locale.](../../media/local-configuration-store.png)
     - Esaminare i risultati e verificare che lo stato dell'attività sia stato completato. Esaminare il file di registro risultante facendo clic su **Visualizza registro**.
     ![Lo stato delle attività viene visualizzato come completato](../../media/local-configuration-task-completed.png)
     - Fare clic su **Fine**.
9. Configurare o rimuovere componenti di Skype for Business Server (passaggio 2):
    - Aprire la distribuzione guidata, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**, quindi fare clic su **Esegui** al passaggio 2: configurare o rimuovere componenti di Skype for Business Server
    - Fare clic su **Avanti** nella finestra di dialogo Configura componenti di Skype for Business Server.
    ![la finestra Configura componenti di Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)
    - Esaminare il registro tramite la visualizzazione log e verificare che l'installazione sia stata completata senza problemi. 
    - Fare clic su **Fine**.
10. Procedere con l'installazione e la configurazione aggiuntive in base alle esigenze (è possibile riprendere le normali procedure di installazione a questo punto).
