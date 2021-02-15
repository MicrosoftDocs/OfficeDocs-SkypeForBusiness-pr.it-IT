---
title: Condivisione dello schermo basata su video per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informazioni sulla pianificazione e la configurazione di Skype for Business Server per la condivisione dello schermo basata su video (VbSS)
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832766"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Condivisione dello schermo basata su video per Skype for Business Server 
 
Video-based Screen Sharing (VbSS) in Skype for Business Server 2015 is now available for download: [Skype for Business Server 2015 cumulative update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS è incluso in Skype for Business Server 2019.
  
La condivisione dello schermo basata su video, o VbSS, è stata la prima a uscire dalla condivisione dello schermo di Lync. La differenza tra VbSS e la condivisione dello schermo tradizionale ha a che fare con i protocolli sottostanti usati e con le caratteristiche più comuni. La condivisione dello schermo utilizza il protocollo RDP (Remote Desktop Protocol), che consente di creare migliaia di sessioni da 1 a 1 tra i computer degli utenti. Una tecnologia più recente, VbSS, utilizzerà il protocollo UDP (User Datagram Protocol).
  
Skype for Business Server desiderava migliorare l'esperienza 1-a-1 delle persone, le conversazioni uno-a-molti (tra più partecipanti) e le esperienze di riunione. VbSS si avvale della piattaforma multimediale (che si basa su UDP come protocollo sottostante), con l'obiettivo di migliorare i tempi di inizio dei video, la qualità di visualizzazione di ciò che stai osservando (soprattutto se ciò che stai osservando sta muovendo velocemente) e l'affidabilità complessiva.
  
Parte dell'obiettivo di migliorare la condivisione dello schermo è che le transizioni tra VbSS e RDP siano il più semplici possibile quando si verificano. Poiché VbSS è un aggiornamento alla tecnologia sottostante utilizzata nella condivisione dello schermo per Skype for Business Server, può essere difficile rilevare quale tecnologia si sta sfruttando, a meno che non si stanno esaminando i dettagli SIP nel traffico di rete o si sta condividendo contenuto in movimento rapido o 3D. Se, ad esempio, l'area di lavoro include molti client legacy, RDP sarà comunque disponibile come failsafe per le riunioni e le conversazioni. Skype for Business Server usa la logica interna per decidere quale dei due metodi (VbSS o condivisione dello schermo tradizionale) applicare quando i client si connettono. RDP può e verrà sostituito con VbSS quando la situazione lo richiede, in modo che l'esperienza di visualizzazione non verrà interrotta.
  
## <a name="planning"></a>Pianificazione

### <a name="vbss-pros-and-cons"></a>Vantaggi e contro vbss

Il passaggio a VbSS ha lo scopo di apportare tre miglioramenti chiave:
  
1. Effettuare la condivisione dello schermo (fino al 5%) più affidabile rispetto al solo RDP.

2. Rendere l'installazione della sessione e l'esperienza video più veloci rispetto al solo RDP (configurazione in metà del tempo, con un miglioramento di 6:1 fotogrammi al secondo).

3. Funziona molto meglio di RDP in condizioni di larghezza di banda ridotta, anche quando si condividono contenuti ad alto movimento, ad esempio grafica 3D.
    
Tieni presente che questi numeri si basano sull'integrità e sull'ottimizzazione delle prestazioni della rete e possono coinvolgere reti esterne alla tua, se i client sono su dispositivi mobili.
  
È inoltre necessario tenere presente che la fedeltà e la nitidezza del contenuto condiviso sono state scambiate per affidabilità, velocità ed efficienza. Nella maggior parte dei casi questo non sarà immediatamente visibile agli utenti.
  
### <a name="ports-and-protocols"></a>Porte e protocolli

**Porte server necessarie**

|**Ruolo del server**|**Nome del servizio**|**Porta o intervallo di porte**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Front End Server  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |5065  <br/> |TCP  <br/> |Utilizzata per le richieste di attesa SIP in arrivo per la condivisione delle applicazioni.  <br/> |
|Front End Server  <br/> |Servizio di condivisione applicazioni di Skype for Business Server  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Intervallo di porte di attesa multimediali per la condivisione delle applicazioni.  <br/> |
   
**Porte client necessarie**

|**Componente**|**Intervallo di porte**|**Protocollo**|**Note**|
|:-----|:-----|:-----|:-----|
|Client  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Condivisione applicazioni.  <br/> |
   
Se QoS è abilitato per le porte multimediali seguenti e è abilitato anche VbSS, durante una conferenza che include la condivisione desktop, la MCU AS utilizzerà le impostazioni della porta video mostrate in grassetto di seguito per il traffico di condivisione dello schermo. 
  
> [!IMPORTANT]
> Queste impostazioni sono un caso speciale e queste impostazioni esatte devono essere utilizzate quando si implementano entrambe queste funzionalità. In questo modo vengono sovrascritte le altre impostazioni consigliate nella [documentazione relativa a QoS.](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx) Per la condivisione di applicazioni è inoltre necessario specificare ASMCUSVC.exe nell'oggetto Criteri di gruppo QoS oltre a definire questi valori di porta. 
  
**Impostazioni necessarie QoS/VbSS del server applicazioni**

|**Proprietà**|**Valore della porta**|**Protocollo**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Pianificazione della capacità

Ogni Front End Server che esegue Skype for Business Server 2015 Cumulative Update 2 (CU2) o versione successiva supporta fino a 375 partecipanti per la condivisione dello schermo tramite RDP (anche se solo 250 per riunione). Questa capacità non cambia dopo l'cu3, quando viene introdotto e utilizzato VbSS.
  
Detto questo, abbiamo eseguito test delle prestazioni e dello stress nel nostro laboratorio e le misurazioni seguenti devono essere considerate anche per quanto riguarda la tua distribuzione (a seconda dell'utilizzo, naturalmente).
  
Presupponendo che:
  
- You're using Skype for Business Server 2015 CU2 or later in your deployment.
    
- Tutti gli utenti nell'ambiente Skype for Business Server hanno risoluzioni dello schermo superiori a 1920x1080.
    
A piena capacità (come indicato in precedenza, è di 375 partecipanti alla condivisione dello schermo per Front End Server in totale, anche se solo 250 per riunione), il Front End Server potrebbe utilizzare circa l'89% dei 1 Gigabit della scheda di rete. Questo perché la tecnologia di condivisione dello schermo esistente in Skype for Business Server CU2 (RDP) trasmette il contenuto sullo schermo con la risoluzione nativa del PC del relatore. Pertanto, con risoluzioni dello schermo più elevate, potrebbero già verificarsi colli di bottiglia di rete per la condivisione dello schermo con Skype for Business Server 2015 CU2.
  
Per ovviare a questo problema, può essere utile una o più delle opzioni seguenti:
  
- Aggiornare il Front End Server da una scheda di rete da 1 Gigabit a una scheda Ethernet da 10 Gigabit.

- Aumentare il numero di Front End Server per bilanciare il carico del traffico.

- Limitare la larghezza di banda (velocità in bit) utilizzata per VbSS e RDP impostando un limite per la larghezza di banda massima utilizzata da entrambi i canali.
    
I numeri in questa tabella sono influenzati dalle singole reti e dal contenuto condiviso. Testare per stabilire le linee di base per la rete o le reti.
  
|**Contenuto 1080p**|**Media RDP**|**Picco RDP**|**VbSS Average**|**VbSS Peak**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12 mbps  <br/> |100kbps  <br/> |3 mbps  <br/> |
|CAD  <br/> |3 mbps  <br/> |7 mbps  <br/> |1 mbps  <br/> |3 mbps  <br/> |
|Video  <br/> |5 mbps  <br/> |7 mbps  <br/> |1,3 mbps  <br/> |2,2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisiti di larghezza di banda di rete per il traffico multimediale

La larghezza di banda vbss è:
  
|**Codec video**|**Risoluzione e proporzioni**|**Velocità in bit massima del payload video (Kbps)**|**Velocità in bit minima del payload video (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> Le proporzioni dipendono dalla risoluzione del monitor del condivisore e non sempre saranno 16:9.  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Supporto per client e server

La condivisione dello schermo basata su video richiede Skype for Business Server 2015 CU3 o versione successiva e una versione corrente dei client di supporto elencati nel confronto delle funzionalità dei client mobili per il supporto di [Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) e [Meetings.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) 
  
Esistono situazioni in cui la condivisione dello schermo passa a RDP, come nel caso seguente:
  
- Se l'account è ospitato in un ambiente in cui ASMCU non soddisfa la build minima che supporta VbSS.
- Se qualcuno che usa una versione precedente del client Skype for Business partecipa alla sessione, ad esempio chiunque usi una versione client di Windows inferiore a 16.0.6330.1000, Dispositivi di sistema sala Skype for Business o App per dispositivi mobili Skype for Business. 
- Se un utente condivide da Skype for Business Web App.
- If someone is using Skype for Business on Mac and not is homed on Skype for Business Online or Skype for Business Server 2015 with the July, 2018 cumulative update (or later).
- Se qualcuno avvia condivisione programmi/Windows.
- Se qualcuno inizia a registrare la sessione.
- Se qualcuno richiama Remote Screen Control durante la sessione. 
- Riunioni con più di 250 partecipanti (dove vbss non è attualmente supportato).

Tenere presente che una volta che la sessione passa a RDP, non tornerà a VbSS. Anche in questo caso, la transizione da VbSS è stata concepita per essere facile e, con la mia intenzione, non sarà facile da rilevare nella maggior parte delle situazioni.
    
> [!NOTE]
> Non è supportato bloccare o tentare di bloccare la transizione da VbSS a RDP nella condivisione dello schermo di Skype for Business. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Abilitazione, disabilitazione e configurazione di VbSS

La cosa migliore è che, dopo aver installato l'aggiornamento cumulativo 3 (CU3) per Skype for Business Server 2015 o versione successiva, tutti gli utenti saranno abilitati per la versione 1-to-1 e per la sicurezza basata su più parti per impostazione predefinita. Questo può essere problematico se hai un motivo per non avere questa funzionalità abilitata per tutti gli utenti. In tal caso, è possibile utilizzare questi passaggi per disabilitare gli utenti (la procedura per abilitare gli utenti sarà la seguente):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Come disabilitare l'utilizzo di VbSS da parte degli utenti

- È possibile assegnare un criterio utente che non consente vbsS agli utenti che non devono usare VbSS eseguendo questo cmdlet in Skype for Business Management Console (sostituire [PolicyName] con il criterio per cui si sta eseguendo questa operazione):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- È inoltre possibile aggiornare il criterio di conferenza globale, che influirà su tutti gli utenti senza un criterio assegnato:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Per ulteriori informazioni su questo comando, [vedere Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
    
- Se è necessario disattivare completamente VbSS, è possibile eseguire questo comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Per ulteriori informazioni su questo comando, [vedere Set-CsMediaConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)
    
> [!NOTE]
> In una riunione Skype for Business con più partecipanti, tutti gli endpoint client rispetteranno l'impostazione dei criteri per l'organizzatore della riunione. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Come consentire agli utenti di usare VbSS

- È possibile assegnare un criterio utente specifico che consenta la sicurezza dei dati a tutti gli utenti che devono usare VbSS eseguendo questo cmdlet in Skype for Business Management Console (sostituire [PolicyName] con il criterio per cui si sta eseguendo questa operazione):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- È inoltre possibile aggiornare il criterio di conferenza globale, che influirà su tutti gli utenti senza un criterio assegnato:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Per ulteriori informazioni su questo comando, [vedere Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
    
- Se devi riattivare VbSS dopo la disattivazione (è attivata per impostazione predefinita), puoi eseguire questo comando:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Per ulteriori informazioni su questo comando, [vedere Set-CsMediaConfiguration.](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)
    
> [!NOTE]
> In una riunione Skype for Business tra più parti, tutti gli endpoint client rispetteranno l'impostazione dei criteri per l'organizzatore della riunione. 
  
## <a name="see-also"></a>Vedere anche

[Aggiornamento cumulativo di Skype for Business Server 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[La condivisione dello schermo basata su video (VBSS) è disponibile in Skype for Business Server 2015](https://support.microsoft.com/kb/3170163)
