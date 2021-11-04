---
title: Distribuire il monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Riepilogo: informazioni su come distribuire il monitoraggio in Skype for Business Server.'
ms.openlocfilehash: cbb5fe0974e1b02ce5be472ba91d01221fb7df82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764844"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Distribuire il monitoraggio in Skype for Business Server

**Riepilogo:** Informazioni su come distribuire il monitoraggio in Skype for Business Server.

Prima di eseguire queste attività, vedere [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).

I servizi di monitoraggio verranno in genere implementati all'interno della topologia completando i due passaggi seguenti:

1. Abilitazione del monitoraggio contemporaneamente alla configurazione di un nuovo pool Skype for Business Server locale. In Skype for Business Server, il monitoraggio è abilitato o disabilitato in base al pool. Si noti che è possibile abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo illustrato nella sezione Configurazione della registrazione dettagli chiamata e della qualità dell'esperienza Impostazioni di questa documentazione.

2. Associazione di un archivio (database) di monitoraggio al nuovo pool. Tenere presente che un archivio di monitoraggio può essere associato a più pool. A seconda del numero di utenti ospitati nei pool di registrazione, questo comporta che non è necessario configurare un database di monitoraggio separato per ogni pool, ma un singolo archivio di monitoraggio può essere utilizzato da più pool.

Sebbene spesso risulti più semplice abilitare il monitoraggio al momento della creazione di un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato. In questo caso, è possibile abilitare il servizio in un secondo momento utilizzando il Generatore di topologie, che consente di attivare o disattivare il monitoraggio di topologie o di associare un pool a un diverso archivio di monitoraggio. Tenere presente che, anche se non è più presente un ruolo monitoring server, sarà comunque necessario creare uno o più archivi di monitoraggio: database back-end utilizzati per archiviare i dati raccolti dal servizio di monitoraggio. Questi database back-end possono essere creati utilizzando Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 o Microsoft SQL Server 2019.

> [!NOTE]
> Se il monitoraggio è stato abilitato per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza dover modificare la topologia: Skype for Business Server consente di disabilitare (e quindi riattivare) la raccolta dati di Registrazione dettagli chiamata (CDR) o QoE (Quality of Experience). Per ulteriori informazioni, vedere la sezione relativa alla configurazione delle impostazioni di registrazione dettagli chiamata e QoE di questa documentazione.

Un altro importante miglioramento del monitoraggio in Skype for Business Server è il fatto che i report di monitoraggio di Skype for Business Server supportano ora IPv6: i report che utilizzano il campo Indirizzo IP visualizzano gli indirizzi IPv4 o IPv6 a seconda di : 1) la query SQL utilizzata; e 2) in cui l'indirizzo IPv6 è archiviato o meno nel database di monitoraggio.

> [!NOTE]
> Verificare che il tipo di avvio del servizio agente di SQL Server sia Automatico e che il servizio agente SQL Server sia in esecuzione per l'istanza di SQL che contiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti in base alla pianificazione sotto il controllo del servizio agente di SQL Server.

Questa documentazione illustra il processo di installazione e configurazione dei report di monitoraggio e monitoraggio per Skype for Business Server. Sono fornite istruzioni dettagliate per le seguenti operazioni:

- Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front End.

- Installare SQL Server Reporting Services e i report Skype for Business Server monitoraggio. I report di monitoraggio sono report preconfigurati che forniscono visualizzazioni diverse nelle informazioni archiviate in un database di monitoraggio.

- Configurare la registrazione dettagli chiamata (CDR) e la raccolta dei dati QoE (Quality of Experience). La registrazione dettagli chiamata consente di tenere traccia dell'utilizzo di funzionalità Skype for Business Server quali le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea; trasferimenti di file; audio/video (A/V) conferencing; e sessioni di condivisione delle applicazioni. Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "instabilità" (differenze nel ritardo dei pacchetti.

- Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.

## <a name="deployment-checklist-for-monitoring"></a>Elenco di controllo per la distribuzione per il monitoraggio

Anche se il monitoraggio è già installato e attivato in ogni Front End Server, è comunque necessario eseguire diversi passaggi prima di poter effettivamente raccogliere i dati di monitoraggio per Skype for Business Server. Questi passaggi sono descritti nell'elenco di controllo seguente:

|**Fase**|**Procedura**|**Appartenenza a gruppi e ruoli**.|**Documentazione**|
|:-----|:-----|:-----|:-----|
|**Installare l'hardware e il software prerequisiti** <br/> |Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.  <br/> |Utente di dominio membro del gruppo administrators locale.  <br/> |[Hardware supportato](/previous-versions/office/lync-server-2013/lync-server-2013-supported-hardware) <br/> [Supporto dell'infrastruttura e del software server](/previous-versions/office/lync-server-2013/lync-server-2013-server-software-and-infrastructure-support) <br/> |
|**Creare la topologia interna appropriata per supportare il monitoraggio** <br/> |Utilizzare Skype for Business Server Generatore di topologie per aggiungere database di monitoraggio alla topologia e quindi pubblicare la topologia aggiornata.  <br/> |Per definire una topologia, un utente membro del gruppo di utenti locali.  <br/> Per pubblicare la topologia, un utente membro del gruppo degli amministratori di dominio e del gruppo RTCUniversalServerAdmins.  <br/> |[Associare un archivio di monitoraggio a un pool Front End in Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Abilitare le impostazioni di monitoraggio appropriate** <br/> |Abilitare la registrazione dettagli chiamata (CDR) e/o il monitoraggio della qualità dell'esperienza (QoE) nell'ambito globale e/o del sito.  <br/> |Utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che consente l'accesso ai cmdlet CsCdrConfiguration e CsQoEConfiguration.  <br/> |[Configurare le impostazioni di registrazione dettagli chiamata e qualità dell'esperienza in Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Abilitare il monitoraggio

Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni Front End Server, ciò non significa che si inizierà automaticamente a raccogliere i dati di monitoraggio al termine dell'installazione Skype for Business Server. È invece necessario eseguire due operazioni: è necessario associare i Front End Server/pool Front End a un database di monitoraggio e abilitare la registrazione dettagli chiamata e/o il monitoraggio della qualità dell'esperienza (QoE) nell'ambito globale e/o nell'ambito del sito.

Per istruzioni dettagliate sull'associazione di Front End Server o pool Front End a un database di monitoraggio, vedere l'argomento Associare un archivio di monitoraggio a un pool Front End in Skype for Business Server nella guida [alla distribuzione.](associate-a-monitoring-store.md) Dopo aver creato queste associazioni e dopo la pubblicazione della nuova topologia di Skype for Business Server, non sarà ancora possibile raccogliere i dati di monitoraggio. Ciò è dovuto al fatto che, per impostazione predefinita, la raccolta dei dati sia cdR che QoE è disabilitata quando si installa Skype for Business Server.

Per iniziare la raccolta dei dati, è necessario abilitare il monitoraggio di registrazione dettagli chiamata e/o QoE. Si noti che non è necessario abilitare sia il monitoraggio cdR che il monitoraggio QoE. Se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Per abilitare il monitoraggio della registrazione dei dati nell'ambito globale, eseguire il comando seguente da Skype for Business Server Management Shell:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

In alternativa, è possibile abilitare il monitoraggio della registrazione dei dati dall'interno Skype for Business Server pannello di controllo. Dal Pannello di controllo Skype for Business Server, completare la procedura seguente:

1. Fare clic su **Monitoraggio**.

2. Nella scheda **Registrazione dettagli chiamata** fare doppio clic sull'impostazione **Globale**.

3. Nel riquadro **Modifica impostazione di registrazione dettagli chiamata** selezionare **Abilita monitoraggio registrazioni dettagli chiamata** e fare clic su **Commit**.

Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando da Skype for Business Server Management Shell:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se preferisci, puoi anche abilitare il monitoraggio QoE dal Pannello Skype for Business Server controllo. Dal Pannello di controllo, completare la procedura seguente:

1. Fare clic su **Monitoraggio**.

2. Nella scheda **Dati QoE** fare doppio clic sull'impostazione **Globale**.

3. Nel riquadro **Modifica impostazione QoE** selezionare **Abilita monitoraggio dei dati QoE** e fare clic su **Commit**.

Come si può notare, negli esempi precedenti il monitoraggio viene abilitato nell'ambito globale, ciò significa che il monitoraggio di registrazione dettagli chiamata e QoE viene abilitato per l'intera organizzazione. In alternativa, è possibile creare impostazioni di configurazione di registrazione dettagli chiamata e QoE nell'ambito del sito, quindi abilitare o disabilitare in modo selettivo per ogni sito. Ad esempio, è possibile abilitare il monitoraggio di registrazione dettagli chiamata per il sito di Parigi, ma disabilitarlo per il sito di Milano. Per ulteriori informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento Guida alla distribuzione Configurare la registrazione dettagli chiamata e le impostazioni [di qualità dell'esperienza in Skype for Business Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Vedere anche

[Pianificare il monitoraggio in Skype for Business Server](../../plan-your-deployment/monitoring.md)