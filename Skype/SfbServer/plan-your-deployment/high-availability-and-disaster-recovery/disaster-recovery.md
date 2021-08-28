---
title: Ripristino di emergenza del pool Front End in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: Per il ripristino di emergenza, Skype for Business Server l'associazione del pool con il failover nel caso in cui un pool si insedi.
ms.openlocfilehash: 728419a20fe99db004b739e599355c9b64a8844f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603835"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Ripristino di emergenza del pool Front End in Skype for Business Server
 
Per il ripristino di emergenza, Skype for Business Server l'associazione del pool con il failover nel caso in cui un pool si insedi.
  
Per le opzioni di ripristino di emergenza più affidabili in Skype for Business Server, distribuire coppie di pool Front End in due siti geograficamente dislocati. Ogni sito dispone di un pool Front End associato a un pool Front End corrispondente nell'altro sito. Entrambi i siti sono attivi e il servizio di backup fornisce la replica dei dati in tempo reale per mantenere sincronizzati i pool. Vedere [Deploy paired Front End pools for disaster recovery in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md) se si desidera implementare l'associazione di pool Front End.
  
![Mostra pool Front End in due siti diversi, abbinati tra loro](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
Se il pool in un sito ha esito negativo, è possibile eseguire il failover degli utenti da tale pool al pool nell'altro sito, che quindi serve tutti gli utenti in entrambi i pool. Per la pianificazione della capacità, è consigliabile progettare ogni pool in modo che sia in grado di gestire il carico di lavoro di tutti gli utenti in entrambi i pool in caso di emergenza.
  
Due data center che includono pool Front End abbinati tra loro possono essere a qualsiasi distanza. È consigliabile associare due data center nella stessa area geografica mondiale, con collegamenti ad alta velocità tra di essi. 
  
La presenza di due data center in aree geografiche del mondo è possibile, ma potrebbe verificarsi una perdita di dati maggiore in caso di emergenza, a causa della latenza nella replica dei dati.
  
Quando si pianificano i pool da associare, è necessario tenere presente che sono supportati solo gli abbinamenti seguenti:
  
- I pool Enterprise Edition possono essere abbinati solo ad altri pool Enterprise Edition. Analogamente, i pool Standard Edition sono abbinabili solo ad altri pool Standard Edition.
    
- I pool fisici possono essere abbinati solo ad altri pool fisici. Analogamente, i pool virtuali sono abbinabili solo ad altri pool virtuali.
    
- I pool abbinati devono eseguire lo stesso sistema operativo di base.
    
È possibile abbinare due pool in un modo diverso da quanto consigliato sia nel Generatore di topologie sia durante la convalida della topologia. Il Generatore di topologie, ad esempio, consente di abbinare un pool Enterprise Edition a un pool Standard Edition. Tuttavia, questi tipi di abbinamenti non sono supportati.
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>Relazioni di registrazione di backup e Survivable Branch Appliance

Oltre ad offrire funzioni di ripristino di emergenza, due pool accoppiati funzionano come registrar di backup l'uno per l'altro. Ogni pool può essere il backup di un solo altro pool Front End.
  
Anche se le relazioni di backup tra due pool Front End devono essere 1:1 e simmetriche, ogni pool Front End può comunque essere anche il registrar di backup per qualsiasi numero di Survivable Branch Appliance.
  
Tenere presente Skype for Business non estende il supporto per il ripristino di emergenza agli utenti ospitati in un Survivable Branch Appliance. Se un pool Front End che funge da backup per un Survivable Branch Appliance non funziona, gli utenti che hanno eseguito l'accesso al Survivable Branch Appliance cadono in modalità resilienza anche se gli utenti ospitati nel pool Front End vengono evasi nel pool Front End di backup.
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>Tempo di ripristino per il failover del pool e il failback del pool

Per il failover del pool e il failback del pool, l'obiettivo di progettazione per l'obiettivo del tempo di ripristino (RTO) è 15-20 minuti. Questo è il tempo necessario per l'esecuzione del failover, dopo che gli amministratori hanno determinato che si è verificata un'emergenza e avviato le procedure di failover. Non include il tempo necessario agli amministratori per valutare la situazione e prendere decisioni né quello impiegato dagli utenti per ripetere l'accesso dopo il completamento del failover.
  
Per il failover del pool e il failback del pool, l'obiettivo di progettazione per l'obiettivo del punto di ripristino (RPO) è 5 minuti. Questo valore rappresenta la misura temporale dei dati che potrebbero essere persi a causa dell'emergenza, in virtù della latenza della replica del servizio di backup. Ad esempio, se un pool scende alle 10.00 e l'RPO è di 5 minuti, i dati scritti nel pool tra le 9.55. e le 10.00 potrebbero non essere state replicate nel pool di backup e andrebbero perse.
  
Tutti i numeri degli obiettivi relativi al tempo e al punto di ripristino riportati in questo documento presuppongono che i due data center si trovino nella medesima area geografica con trasporto ad alta velocità e bassa latenza tra i siti. Questi numeri vengono misurati per un pool con 40.000 utenti attivi contemporaneamente e 200.000 utenti abilitati per Skype for Business rispetto a un modello utente predefinito in cui non è presente alcun backlog nella replica dei dati. Le cifre sono soggette a modifiche a seconda dei test e della convalida delle prestazioni.
  
## <a name="central-management-store-failover"></a>Failover dell'archivio di gestione centrale

L'archivio di gestione centrale contiene i dati di configurazione relativi ai server e ai servizi nella distribuzione. Ogni Skype for Business Server distribuzione include un archivio di gestione centrale, ospitato dal server back-end di un pool Front End.
  
Se si associa il pool che ospita l'archivio di gestione centrale, nel pool di backup viene impostato un database dell'archivio di gestione centrale di backup. In qualsiasi momento, uno dei due database dell'archivio di gestione centrale è attivo e l'altro è di standby. Il contenuto viene replicato dal servizio di backup dal database attivo alla modalità standby.
  
![Mostra due pool Front End, uno con l'archivio CMS attivo e l'altro con l'archivio CMS di backup passivo](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
Durante un failover del pool che coinvolge il pool che ospita l'archivio di gestione centrale, è necessario eseguire il failover dell'archivio di gestione centrale prima di eseguire il failover del pool Front End.
  
Dopo il ripristino dell'emergenza, non è necessario eseguire il fail back dell'archivio di gestione centrale. L'archivio di gestione centrale può rimanere nel pool a cui è stato superato il tentativo.
  
Gli obiettivi di progettazione per il failover dell'archivio di gestione centrale sono 5 minuti per l'obiettivo del tempo di ripristino (RTO) e 5 minuti per l'obiettivo del punto di ripristino (RPO).
  
## <a name="front-end-pool-pairing-data-security"></a>Sicurezza dei dati di associazione del pool Front End

Il servizio di backup trasferisce continuamente i dati utente e il contenuto delle conferenze tra due pool Front End abbinati. I dati utente contengono GLI URI SIP dell'utente, nonché pianificazioni di conferenze, elenchi di contatti e impostazioni. Il contenuto delle conferenze include i caricamenti di microsoft PowerPoint e le lavagne usate nelle conferenze.
  
Dal pool di origine, questi dati vengono esportati dall'archiviazione locale, compressi e quindi trasferiti nel pool di destinazione, dove vengono decompressi e importati nell'archiviazione locale. Il Servizio di backup presume che i collegamenti di comunicazione tra i due data center si trovino all'interno di una rete aziendale protetta da Internet. Non crittografa i dati trasferiti tra i due data center, né i dati incapsulati in modo nativo all'interno di un protocollo sicuro, ad esempio HTTPS. Pertanto, è possibile un attacco man-in-the-middle da parte del personale interno all'interno della rete aziendale.
  
Qualsiasi azienda che distribuisce Skype for Business Server più data center e utilizza la funzionalità di ripristino di emergenza deve garantire che il traffico tra i data center sia protetto dalla rete Intranet aziendale. Le aziende che si preoccupano della protezione da attacchi interni devono proteggere i collegamenti di comunicazione tra i data center. Si tratta di un requisito standard che aiuta anche protech molti altri tipi di dati sensibili aziendali trasferiti tra data center.
  
Sebbene in un'azienda esista il pericolo di attacchi man-in-the-middle, è relativamente contenuto se paragonato al rischio di esporre il traffico in Internet. In particolare, i dati utente esposti dal servizio di backup (ad esempio gli URI SIP) sono generalmente disponibili per tutti i dipendenti della società tramite altri mezzi, ad esempio la Rubrica globale o altro software di directory. Pertanto, l'attenzione deve essere concentrata sulla protezione della rete WAN tra i due data center quando viene utilizzato il servizio di backup per copiare i dati tra i due pool associati.
  
### <a name="mitigating-security-risks"></a>Riduzione dei rischi per la sicurezza

Sono disponibili molti modi per migliorare la protezione del traffico del servizio di backup. Ciò va dalla limitazione dell'accesso ai data center alla protezione del trasporto WAN tra i due data center. Nella maggior parte dei casi, le aziende che distribuiscono Skype for Business Server potrebbero già disporre dell'infrastruttura di sicurezza necessaria. Per le aziende che cercano indicazioni, Microsoft fornisce una soluzione come esempio di come creare un'infrastruttura IT sicura. Per informazioni dettagliate, vedere [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)) . 
  
Non implica che sia l'unica soluzione, né che sia la soluzione preferita per Skype for Business Server. È consigliabile che i clienti aziendali scelsino la soluzione in base alle proprie esigenze specifiche, in base all'infrastruttura e ai requisiti di sicurezza IT. La soluzione Microsoft di esempio utilizza IPSec e Criteri di gruppo per l'isolamento del server e del dominio.
  
Un'altra soluzione possibile consiste nell'utilizzare IPSec solo per proteggere i dati inviati dal servizio di backup stesso. Se si sceglie questo metodo, è necessario configurare le regole IPSec per il protocollo SMB per i server seguenti, dove Pool A e Pool B sono due pool Front End abbinati.
  
- Il servizio SMB (TCP/445) da ogni Front End Server nel pool A all'archivio file utilizzato dal pool B.
    
- Il servizio SMB (TCP/445) da ogni Front End Server nel pool B all'archivio file utilizzato dal pool A.
    
> [!CAUTION]
>  IPsec non è destinato a sostituire la sicurezza a livello di applicazione, ad esempio SSL/TLS. Un vantaggio dell'utilizzo di IPsec è che può garantire la sicurezza del traffico di rete per le applicazioni esistenti senza doverle modificare. Le aziende che desiderano proteggere semplicemente il trasporto tra i due data center devono consultare i rispettivi fornitori di hardware di rete su come configurare connessioni WAN protette utilizzando le attrezzature del fornitore.
  
## <a name="see-also"></a>Vedere anche

[Distribuire pool Front End associati per il ripristino di emergenza in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)