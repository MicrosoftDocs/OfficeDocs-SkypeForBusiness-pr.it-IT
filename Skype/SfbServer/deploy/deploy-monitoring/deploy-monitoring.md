---
title: Distribuire il monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Riepilogo: informazioni su come distribuire il monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 89474b7d40a63911c6a79bee719573516a9d423a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802276"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Distribuire il monitoraggio in Skype for Business Server

**Riepilogo:** Informazioni su come distribuire il monitoraggio in Skype for Business Server.

Prima di eseguire queste attività, esaminare [piano per il monitoraggio in Skype for Business Server](../../plan-your-deployment/monitoring.md).

In genere, i servizi di monitoraggio all'interno della topologia vengono implementati completando i due passaggi seguenti:

1. Attivazione del monitoraggio nello stesso momento in cui si configura un nuovo pool di Skype for Business Server. In Skype for Business Server, il monitoraggio è abilitato o disabilitato in base al pool. Si noti che è possibile abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo illustrato nella sezione Configurazione delle impostazioni di registrazione dettagli chiamata e qualità di esperienza di questa documentazione.

2. Associazione di un archivio (database) di monitoraggio al nuovo pool. Tenere presente che un archivio di monitoraggio può essere associato a più pool. A seconda del numero di utenti ospitati nei pool di registrazione, questo comporta che non è necessario configurare un database di monitoraggio separato per ogni pool, ma un singolo archivio di monitoraggio può essere utilizzato da più pool.

Sebbene spesso risulti più semplice abilitare il monitoraggio al momento della creazione di un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato. In questo caso, è possibile abilitare il servizio in un secondo momento utilizzando il Generatore di topologie, che consente di attivare o disattivare il monitoraggio di topologie o di associare un pool a un diverso archivio di monitoraggio. Tenere presente che, anche se non è più presente un ruolo di Monitoring Server, sarà comunque necessario creare uno o più archivi di monitoraggio: i database back-end utilizzati per archiviare i dati raccolti dal servizio di monitoraggio. È possibile creare questi database back-end utilizzando Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012, Microsoft SQL Server 2014 o Microsoft SQL Server 2019.

> [!NOTE]
> Se è stato abilitato il monitoraggio per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza dover modificare la topologia: Skype for Business Server consente di disabilitare (e successivamente riabilitare) la raccolta dei dati di registrazione dettagli chiamata (CDR) o la qualità di esperienza (QoE). Per ulteriori informazioni, vedere la sezione relativa alla configurazione delle impostazioni di registrazione dettagli chiamata e QoE di questa documentazione.

Un altro importante miglioramento del monitoraggio in Skype for Business Server è il fatto che i rapporti di monitoraggio di Skype for Business Server ora supportano IPv6: i report che utilizzano il campo indirizzo IP visualizzeranno gli indirizzi IPv4 o IPv6 a seconda di quanto segue: 1) la query SQL utilizzata. e 2) dove l'indirizzo IPv6 è memorizzato o meno nel database di monitoraggio.

> [!NOTE]
> Verificare che il tipo di avvio del servizio SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza di SQL che contiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti nella loro base pianificata sotto il controllo del servizio SQL Server Agent.

In questa documentazione viene illustrato il processo di installazione e configurazione dei rapporti di monitoraggio e monitoraggio per Skype for Business Server. Sono fornite istruzioni dettagliate per le seguenti operazioni:

- Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front End.

- Installare SQL Server Reporting Services e i report di monitoraggio di Skype for Business Server. I report di monitoraggio sono rapporti preconfigurati che forniscono visualizzazioni diverse nelle informazioni archiviate in un database di monitoraggio.

- Configurare la raccolta dati di registrazione dettagli chiamata (CDR) e la qualità di esperienza (QoE). La registrazione dettagli chiamata consente di monitorare l'utilizzo delle funzionalità di Skype for Business Server, ad esempio le chiamate telefoniche VoIP (Voice over IP). messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e la quantità di "instabilità" (differenze nel ritardo dei pacchetti.

- Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.

## <a name="deployment-checklist-for-monitoring"></a>Elenco di controllo di distribuzione per il monitoraggio

Anche se il monitoraggio è già installato e attivato in ogni Front End Server, è necessario intraprendere alcuni passaggi prima di poter effettivamente raccogliere dati di monitoraggio per Skype for Business Server. Questi passaggi sono descritti nell'elenco di controllo seguente:

|**Fase**|**Procedura**|**Appartenenza a gruppi e ruoli**.|**Documentazione**|
|:-----|:-----|:-----|:-----|
|**Installare l'hardware e il software prerequisiti** <br/> |Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.  <br/> |Utente di dominio che è anche membro del gruppo Administrators locale.  <br/> |[Hardware supportato](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Supporto dell'infrastruttura e del software server](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Creare la topologia interna appropriata per supportare il monitoraggio** <br/> |Utilizzare il generatore di topologie di Skype for Business Server per aggiungere database di monitoraggio alla topologia e quindi pubblicare la topologia aggiornata.  <br/> |Per definire una topologia, un utente membro del gruppo utenti locali.  <br/> Per pubblicare la topologia, un utente membro del gruppo Domain Administrators e del gruppo RTCUniversalServerAdmins.  <br/> |[Associare un archivio di monitoraggio a un pool Front end in Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Abilitare le impostazioni di monitoraggio appropriate** <br/> |Abilitare il monitoraggio di registrazione dettagli chiamata (CDR) e/o la qualità di esperienza (QoE) negli ambiti globali e/o del sito.  <br/> |Un utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che fornisce l'accesso ai cmdlet CsCdrConfiguration e CsQoEConfiguration.  <br/> |[Configurare le impostazioni di registrazione dettagli chiamata e qualità delle esperienze in Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Abilitare il monitoraggio

Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente su ogni Front End Server, ciò non significa che si inizierà automaticamente a raccogliere dati di monitoraggio nel momento in cui si finisce di installare Skype for Business Server. Al contrario, è necessario eseguire due operazioni: è necessario associare i Front End Server e i pool Front end a un database di monitoraggio ed è necessario abilitare il monitoraggio di registrazione dettagli chiamata (CDR) e/o la qualità dell'esperienza (QoE) nell'ambito globale e/o nell'ambito del sito.

Per istruzioni dettagliate sull'associazione di front end server o pool Front end a un database di monitoraggio, vedere l'argomento [associare un archivio di monitoraggio a un pool Front end in Skype for Business Server](associate-a-monitoring-store.md) nella Guida alla distribuzione. Dopo aver pubblicato queste associazioni e dopo che è stata pubblicata la nuova topologia di Skype for Business Server, non sarà ancora possibile raccogliere dati di monitoraggio. Ciò è dovuto al fatto che, per impostazione predefinita, sia la raccolta di dati CDR che QoE è disabilitata quando si installa Skype for Business Server.

Per iniziare la raccolta dei dati, è necessario abilitare il monitoraggio di registrazione dettagli chiamata e/o QoE. Tenere presente che non è necessario abilitare il monitoraggio di CDR e QoE, se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato. Per abilitare il monitoraggio CDR nell'ambito globale, eseguire il comando seguente dall'interno di Skype for Business Server Management Shell:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

In alternativa, è possibile abilitare il monitoraggio CDR dall'interno del pannello di controllo di Skype for Business Server. Nel pannello di controllo di Skype for Business Server, eseguire la procedura seguente:

1. Fare clic su **Monitoraggio**.

2. Nella scheda **Registrazione dettagli chiamata** fare doppio clic sull'impostazione **Globale**.

3. Nel riquadro **Modifica impostazione di registrazione dettagli chiamata** selezionare **Abilita monitoraggio registrazioni dettagli chiamata** e fare clic su **Commit**.

Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando dall'interno di Skype for Business Server Management Shell:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se si preferisce, è anche possibile abilitare il monitoraggio QoE dall'interno del pannello di controllo di Skype for Business Server. Dal Pannello di controllo, completare la procedura seguente:

1. Fare clic su **Monitoraggio**.

2. Nella scheda **Dati QoE** fare doppio clic sull'impostazione **Globale**.

3. Nel riquadro **Modifica impostazione QoE** selezionare **Abilita monitoraggio dei dati QoE** e fare clic su **Commit**.

Come si può notare, negli esempi precedenti il monitoraggio viene abilitato nell'ambito globale, ciò significa che il monitoraggio di registrazione dettagli chiamata e QoE viene abilitato per l'intera organizzazione. In alternativa, è possibile creare impostazioni di configurazione di registrazione dettagli chiamata e QoE nell'ambito del sito, quindi abilitare o disabilitare in modo selettivo per ogni sito. Ad esempio, è possibile abilitare il monitoraggio di registrazione dettagli chiamata per il sito di Parigi, ma disabilitarlo per il sito di Milano. Per ulteriori informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento Deployment Guide [Configure Call Detail Recording and Quality of Experience Settings in Skype for Business Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Vedere anche

[Pianificare il monitoraggio in Skype for Business Server](../../plan-your-deployment/monitoring.md)
