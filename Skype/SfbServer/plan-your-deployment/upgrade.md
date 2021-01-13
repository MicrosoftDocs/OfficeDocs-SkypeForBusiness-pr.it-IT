---
title: Pianificare l'aggiornamento a Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c62b5f6a-bdbe-4ac1-aabf-89e560e64a26
description: "Riepilogo: informazioni sugli aspetti da considerare quando si pianifica un aggiornamento a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 da Microsoft Evaluation Center all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 69b1d9df20330ad0baecbc1c5abe59e76808185a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831976"
---
# <a name="plan-to-upgrade-to-skype-for-business-server-2015"></a>Pianificare l'aggiornamento a Skype for Business Server 2015
 
Riepilogo: informazioni sugli aspetti da considerare quando si pianifica un aggiornamento a Skype for Business Server 2015. Scaricare una versione di valutazione gratuita di Skype for Business Server 2015 da Microsoft Evaluation Center all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
Come parte del piano per l'aggiornamento a Skype for Business Server 2015, utilizzare questo argomento per comprendere i percorsi di aggiornamento consigliati per Skype for Business Server 2015, come funziona l'aggiornamento In-Place, quali sono gli scenari di coesistenza supportati e quali sono le caratteristiche del processo di aggiornamento.

> [!NOTE]
> Gli aggiornamenti sul posto sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. La coesistenza fianco a fianco è supportata, vedere [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) per ulteriori informazioni.
  
## <a name="recommended-upgrade-paths-to-skype-for-business-server-2015"></a>Percorsi di aggiornamento consigliati per Skype for Business Server 2015

 Per eseguire l'aggiornamento da Lync Server 2013, Lync Server 2010 o Office Communications Server 2007 R2 a Skype for Business Server 2015, utilizzare i percorsi di aggiornamento seguenti:
  
> [!CAUTION]
> In-Place aggiornamento sposta automaticamente le directory conferenze da Lync Server 2013 a Skype for Business Server 2015. Tuttavia, se si prevede di spostare manualmente le directory conferenze, è molto importante usare Skype for Business Server 2015 Management Shell. Se si tenta di utilizzare Lync Server 2013 Management Shell per spostare le directory conferenze da Lync Server 2013 a Skype for Business Server 2015, è possibile che si verifichi una perdita di dati. In generale, ogni volta che si utilizza Skype for Business Server 2015 in qualsiasi capacità, è necessario utilizzare il set di strumenti di Skype for Business Server 2015.  
  
|**Versione**|**Consigli**|
|:-----|:-----|
|Lync Server 2013  <br/> | Per eseguire l'aggiornamento, utilizzare il generatore di topologie di Skype for Business Server e la nuova funzionalità di aggiornamento In-Place su ciascuno dei server associati al pool. vedere [plan to upgrade from Lync server 2013 to Skype for Business server 2015](upgrade.md#BKMK_PlanUpgradeFromLync2013) e [upgrade to Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md) per la procedura dettagliata. <br/> |
|Lync Server 2010 + Lync Server 2013 (modalità duale)  <br/> |Prima di tutto, eseguire l'aggiornamento a Lync Server 2013 e quindi eseguire l'aggiornamento a Skype for Business Server 2015 utilizzando la nuova funzionalità di aggiornamento In-Place. Tuttavia, se la topologia è Lync Server primario 2010, è anche possibile eseguire il rollback dei componenti di Lync Server 2013 su Lync Server 2010 e quindi eseguire l'aggiornamento direttamente a Skype for Business Server 2015. In questo caso, non è possibile trarre vantaggio dall'aggiornamento In-Place e utilizzare la coesistenza lineare tra Lync Server 2010 e Skype for Business Server 2015. La Tri-esistenza non è supportata ma è supportata la coesistenza.  <br/> |
|Lync Server 2010  <br/> |Aprire un nuovo pool di Skype for Business Server 2015 e quindi eseguire la migrazione degli utenti nel nuovo pool. È quindi possibile rimuovere il vecchio pool Lync Server 2010. L'aggiornamento da Lync Server 2010 a Skype for Business Server 2015 è analogo all'aggiornamento da Lync Server 2010 a Lync Server 2013. Vedere [Migration from Lync server 2010 to Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).  <br/> |
|Office Communications Server 2007 R2  <br/> | Scegliere una delle due opzioni seguenti: <br/>  Configurare un nuovo ambiente di Skype for Business Server 2015. <br/>  Oppure, se l'hardware e il software soddisfano i requisiti per Skype for Business Server 2015, eseguire l'aggiornamento a Lync Server 2013 e quindi eseguire l'aggiornamento a Skype for Business Server 2015 utilizzando la nuova funzionalità di aggiornamento In-Place. Per ulteriori informazioni, vedere [requisiti del server per Skype for Business server 2015](requirements-for-your-environment/server-requirements.md) e [migrazione da Office Communications Server 2007 R2 a Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526616).  <br/> |
   
> [!NOTE]
> SQL Server 2014 è supportato in Skype for Business Server 2015 ma non è supportato in Lync Server 2013. Se si desidera eseguire l'aggiornamento da SQL Server 2012 a SQL Server 2014, è necessario che il pool venga prima aggiornato a Skype for Business Server 2015 utilizzando il metodo di aggiornamento In-Place come descritto in questo documento. È quindi possibile eseguire l'aggiornamento da SQL Server 2012 a SQL Server 2014, vedere [upgrade to SQL server 2014](https://msdn.microsoft.com/library/bb677622%28v=sql.120%29.aspx). Per ulteriori informazioni sui requisiti dei database, vedere [requisiti dei server per Skype for Business server 2015](requirements-for-your-environment/server-requirements.md). 
  
## <a name="plan-to-upgrade-from-lync-server-2013-to-skype-for-business-server-2015"></a>Pianificare l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

È possibile aggiornare i sistemi Lync Server 2013 a Skype for Business Server 2015 utilizzando la nuova funzionalità di aggiornamento In-Place. L'aggiornamento sul posto fornisce una soluzione con un solo clic che consente di eseguire il backup dei certificati, di disinstallare i componenti del server, di aggiornare i database locali e di installare i ruoli di Skype for Business Server 2015. L'aggiornamento sul posto cerca di preservare gli investimenti hardware e server esistenti, riducendo il costo complessivo per la distribuzione di Skype for Business Server 2015.
  
> [!NOTE]
> In-Place upgrade consente di utilizzare lo stesso hardware quando si effettua l'aggiornamento a Skype for Business Server. Tuttavia, il riutilizzo dello stesso hardware non comporta la stessa capacità di prestazioni. Non è necessario attendere che i carichi di prestazioni per Lync Server 2013 e Skype for Business Server 2015 siano identici. 
  
> [!NOTE]
> In-Place aggiornamento non supporta la disponibilità elevata o il ripristino di emergenza per Skype for Business Server. 
  
L'aggiornamento sul posto implica che il pool Lync Server 2013 non è in linea e l'aggiornamento a un pool di Skype for Business Server 2015. 
  
### <a name="create-an-in-place-upgrade-plan"></a>Creare un piano di aggiornamento In-Place

Creare un piano che includa:
  
1. Conoscenza della topologia corrente.
    
    > [!NOTE]
    > Assicurarsi di disinstallare lo strumento di amministrazione di LRS per Lync Server 2013 prima di eseguire In-Place aggiornamento. Lo strumento di amministrazione di LRS per Lync Server 2013 non può coesistere con Skype for Business Server 2015. Dopo aver eseguito In-Place aggiornamento, installare il nuovo strumento di amministrazione di LRS. Per ulteriori informazioni, vedere il [portale Web amministrativo di Microsoft Lync room System per Skype for Business Server 2015](https://go.microsoft.com/fwlink/?LinkID=544807) .
  
2. Pool primario per l'aggiornamento.
    
3. La possibilità di aggiornare i database di archiviazione e monitoraggio o crearne di nuovi.
    
4. Il metodo di aggiornamento In-Place verrà utilizzato: offline o spostamento degli utenti. Come parte degli utenti di spostamento è inoltre necessario eseguire la migrazione delle directory conferenza globale associate al pool primario. 
    
5. Piano di comunicazione per gli utenti interessati.
    
6. Piano di backup in caso di esito negativo degli aggiornamenti.
    
Tutti gli utenti che si trovano nel pool primario durante l'aggiornamento non saranno in grado di utilizzare i servizi fino al completamento dell'aggiornamento. Se si dispone di un pool secondario funzionante, è possibile evitare di influire sugli utenti spostando il pool secondario prima dell'aggiornamento. Dopo l'aggiornamento, spostare nuovamente gli utenti nel pool primario.
  
### <a name="in-place-upgrade-methods"></a>Metodi di aggiornamento sul posto

Esistono due scenari per l'aggiornamento In-Place: 
  
- Il metodo Move utente, che non richiede tempi di inattività per gli utenti. 
    
- Il metodo offline, che richiede tempi di inattività.
    
È consigliabile pianificare l'aggiornamento di un metodo offline durante una finestra di manutenzione e gli utenti ricevono una notifica del tempo di inattività.
  
> [!NOTE]
> Quando si esegue l'aggiornamento di un pool in coppia su Lync Server 2013 e si desidera aggiornare entrambi i pool a Skype for Business Server 2015. Assicurarsi di eseguire l'aggiornamento del secondo pool subito dopo l'aggiornamento del primo pool. Quando un pool esegue Lync Server 2013 e il secondo pool esegue Skype for Business Server 2015, le opzioni di ripristino di emergenza sono ridotte a icona. Ad esempio, se un pool è in esecuzione 2013 e il secondo è 2015 ed è presente un errore, è possibile che si verifichi una perdita di dati perché il failover del pool non è supportato in modalità di emergenza quando i pool associati non sono della stessa versione. 
  
#### <a name="in-place-upgrade-offline-method"></a>Metodo di aggiornamento sul posto offline

Utilizzare questo metodo se non si desidera spostare gli utenti tra i pool di utenti. Durante l'aggiornamento, gli utenti non saranno in grado di utilizzare i servizi Lync o Skype for business. 
  
Nel diagramma seguente viene illustrata una panoramica di questo processo.
  
![Lync 2013 per gli utenti di Skype offline](../media/e5511897-77bc-46aa-96be-85b126d7da79.png)
  
> [!NOTE]
> Se si dispone di pool associati, non disaccoppiarli prima dell'aggiornamento. 
  
Dopo aver avviato l'aggiornamento di un pool di server, è necessario completare l'aggiornamento dell'intero pool. Skype for Business Server non supporta l'utilizzo di solo una parte del pool aggiornato. 
  
#### <a name="move-users-method-no-user-downtime"></a>Metodo Move users (nessun tempo di inattività dell'utente)
<a name="bkmk_MoveUsersMethod"> </a>

Per utilizzare questo metodo, è necessario spostare gli utenti in un altro pool prima di iniziare l'aggiornamento. Durante l'aggiornamento, gli utenti possono utilizzare i servizi Lync. Dopo essere stati spostati nel pool aggiornato, è possibile utilizzare Skype for business. Nel diagramma seguente viene illustrata una panoramica di questo processo.
  
> [!IMPORTANT]
> Come parte degli utenti di spostamento è inoltre necessario eseguire la migrazione delle directory conferenza globale associate al pool primario. Le conferenze telefoniche con accesso esterno PSTN continuano a risolvere ConferenceID al pool che si sta aggiornando, invece del pool associato. Pertanto, è necessario spostare le directory conferenze, se si desidera comunque che le conferenze PSTN pianificate nel pool siano accessibili durante l'aggiornamento. 
  
![Diagramma di nuoto che indica che gli utenti vengono spostati in un altro pool prima che il pool venga aggiornato e venga spostato di nuovo nel pool dopo l'aggiornamento.](../media/7962b3a0-f61a-4340-b8b1-51c20e150d96.png)
  
#### <a name="move-users-for-hardware-upgrade"></a>Spostare gli utenti per l'aggiornamento dell'hardware
<a name="bkmk_MoveUsersMethod"> </a>

 Se l'hardware non soddisfa i [requisiti del server per Skype for Business server 2015](requirements-for-your-environment/server-requirements.md), configurare un nuovo ambiente Skype for business server 2015 e spostare gli utenti. Nel diagramma seguente viene illustrata una panoramica di questo processo per l'aggiornamento da Lync Server 2010. 
  
![Diagramma di corsia di nuoto che visualizza gli utenti del pool Front End primario di Lync Server spostati in Skype for Business Server 2015 e il pool di Lync Server da rimuovere.](../media/5e97ced8-72f4-4925-b09d-bda28a69d448.png)
  
### <a name="in-place-upgrade-process"></a>Processo di aggiornamento sul posto

 Eseguire l'aggiornamento da Lync Server 2013 a Skype for Business Server 2015 seguendo i passaggi seguenti:
  
1. Eseguire il backup di tutti i database prima dell'aggiornamento.
    
2. Verificare che tutti i servizi che devono essere aggiornati siano in stato di esecuzione.
    
3. Aggiornare e pubblicare il file di topologia mediante il generatore di topologie.
    
4. Arrestare tutti i servizi in tutti i Front End Server.
    
5. Installare nuovi prerequisiti richiesti per Skype for Business Server.
    
6. In ogni Front End Server avviare l'aggiornamento In-Place.
    
7. Al termine dell'aggiornamento, riavviare tutti i servizi.
    
   - Per il pool Front End, riavviare i servizi utilizzando il comando Start-CsPool.
    
   - Per i server non front end, utilizzare Start-CSWindowsService.
    
> [!NOTE]
>  Se non si desidera aggiornare i database di archiviazione e di monitoraggio esistenti, rimuovere la dipendenza prima di aggiornare la topologia. Se si desidera creare nuovi database di archiviazione e monitoraggio, durante l'aggiornamento è possibile creare un nuovo archivio SQL e associarlo al pool. È possibile trovare i passaggi su come eseguire questa operazione nell'argomento,[eseguire l'aggiornamento a Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md). > aggiornamento sul posto non supporta la disponibilità elevata o il ripristino di emergenza per Skype for Business Server. Per evitare di interrompere i servizi degli utenti, utilizzare il [Metodo Move users (nessun tempo di inattività dell'utente)](upgrade.md#bkmk_MoveUsersMethod) per eseguire l'aggiornamento. > durante il processo di aggiornamento, la xds-replica viene posizionata nella cartella condivisa locale nell'unità disco con la maggior parte dello spazio disponibile. Se il disco viene successivamente rimosso, è possibile eseguire problemi quali i servizi non avviati.
  
### <a name="upgrade-order"></a>Ordine di aggiornamento

Aggiornare la topologia dall'interno verso l'esterno. Aggiornare innanzitutto tutti i pool, quindi i server perimetrali e infine il pool di archivio di gestione centrale (CMS). 
  
### <a name="kerberos-authentication-considerations"></a>Considerazioni sull'autenticazione Kerberos

Se si utilizza l'autenticazione Kerberos per i servizi Web, è necessario riassegnare gli account Kerberos e reimpostare la password al termine dell'aggiornamento In-Place. Per informazioni su come eseguire questa operazione, vedere [Setting up Kerberos Authentication](https://go.microsoft.com/fwlink/p/?LinkId=530342).
  
## <a name="support-for-coexistence-with-lync-server-2013-and-lync-server-2010"></a>Supporto per la coesistenza con Lync Server 2013 e Lync Server 2010
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

È possibile eseguire Skype for Business Server 2015 nella stessa topologia di Lync Server 2013 o Lync Server 2010, ma non è possibile avere tutti e tre nella stessa topologia.
  
Se si dispone di una coesistenza tra Lync Server 2010 e Lync Server 2013, è consigliabile aggiornare l'intera topologia a Lync Server 2013 e quindi eseguire l'aggiornamento a Skype for Business Server 2015 utilizzando l'aggiornamento In-Place. Per ulteriori informazioni, vedere [migrazione da Lync server 2010 a Lync server 2013](https://go.microsoft.com/fwlink/p/?LinkId=526615).
  
Se la topologia è principalmente Lync Server 2010, eseguire il rollback dei componenti di Lync Server 2013 in Lync Server 2010 prima di aggiornare la topologia a Skype for Business Server 2015. In questo caso, si perde il vantaggio dell'aggiornamento In-Place e si dispone di una topologia di coesistenza tra Lync Server 2010 e Skype for Business Server 2015.
  
Nel diagramma seguente viene illustrato il supporto per la coesistenza di Skype for Business Server 2015 con Lync Server 2013 e Lync Server 2010.
  
![Diagramma che mostra il supporto per la coesistenza per Skype for Business Server 2015 con Lync Server 2013 o Lync Server 2010.](../media/b5eb4f8c-577a-4a45-9a66-9531ce2c5dc1.png)
  
## <a name="upgrade-process-with-existing-survivable-branch-appliance-and-server"></a>Processo di aggiornamento con Survivable Branch Appliance e il server esistente
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

Skype for Business Server 2015 non supporta un aggiornamento In-Place di un Survivable Branch Appliance (SBA) o di un Survivable Branch Server (SBS).
  
Tuttavia, è supportata la coesistenza dei datacenter di Skype for Business Server con Lync Server 2010 o Lync Server 2013 SBA/SBS. 
  
Quando si pianifica un aggiornamento In-Place di un pool di Lync Server 2013 front end (FE) con un ramo associato, è possibile lasciare gli utenti esistenti sul Lync Server 2013 SBA/SBS. Durante l'aggiornamento, gli utenti di SBA/SBS andranno in modalità di resilienza e torneranno alla funzionalità normale dopo che l'aggiornamento è stato completato. Per ulteriori informazioni sull'esperienza degli utenti durante la modalità di resilienza, vedere [funzionalità di resilienza dei siti di succursale in Lync Server 2013](https://technet.microsoft.com/library/gg398715.aspx).
  
Quando si esegue la migrazione di una topologia di Lync Server 2010 in Skype for Business Server 2015, è necessario aggiungere di nuovo la SBA/SBS alla topologia, analogamente alla migrazione a Lync Server 2013. Per i passaggi necessari, leggere [Connecting Survivable Branch Appliance to Lync Server 2013 front end pool](https://technet.microsoft.com/library/jj688026.aspx).
  
Per le topologie di coesistenza di Lync Server 2010 e Lync Server 2013, allineare innanzitutto le indicazioni riportate nella sezione ' supporto per la coesistenza con Lync Server 2013 e Lync Server 2010'.
  
## <a name="see-also"></a>Vedere anche
<a name="BKMK_PlanUpgradeFromLync2013"> </a>

[Eseguire l'aggiornamento a Skype for Business Server 2015](../deploy/upgrade-to-skype-for-business-server.md)
  
[Requisiti ambientali per Skype for Business Server 2015](requirements-for-your-environment/environmental-requirements.md)
  
[Requisiti del server per Skype for Business Server 2015](requirements-for-your-environment/server-requirements.md)
