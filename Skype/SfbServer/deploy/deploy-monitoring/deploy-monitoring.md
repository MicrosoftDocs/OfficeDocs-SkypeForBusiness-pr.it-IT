---
title: Distribuire il monitoraggio in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
description: 'Riepilogo: informazioni su come distribuire il monitoraggio in Skype for Business Server.'
ms.openlocfilehash: 7f3bd96b814b45b625612aae9b56a706dfff470f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001147"
---
# <a name="deploy-monitoring-in-skype-for-business-server"></a>Distribuire il monitoraggio in Skype for Business Server

**Riepilogo:** Informazioni su come distribuire il monitoraggio in Skype for Business Server.

Prima di eseguire queste attività, rivedere il [piano per il monitoraggio in Skype for Business Server](../../plan-your-deployment/monitoring.md).

In genere verranno implementati i servizi di monitoraggio all'interno della topologia completando i due passaggi seguenti:

1. Abilitazione del monitoraggio contemporaneamente alla configurazione di un nuovo pool di Skype for Business Server. In Skype for Business Server il monitoraggio è abilitato o disabilitato in base al pool per pool. Tieni presente che puoi abilitare il monitoraggio per un pool senza raccogliere effettivamente i dati di monitoraggio, un processo spiegato nella sezione configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza di questa documentazione.

2. Associazione di un archivio di monitoraggio (ovvero un database di monitoraggio) con il nuovo pool. Tieni presente che un singolo archivio di monitoraggio può essere associato a più pool. A seconda del numero di utenti ospitati nei pool di registrar, significa che non è necessario configurare un database di monitoraggio separato per ogni pool. Un singolo archivio di monitoraggio può invece essere usato da più pool.

Anche se spesso è più semplice abilitare il monitoraggio quando si crea un nuovo pool, è anche possibile creare un nuovo pool con il monitoraggio disabilitato. In questo caso, puoi usare il generatore di topologie in seguito per abilitare il servizio: generatore di topologie consente di abilitare o disabilitare il monitoraggio per un pool o di associare un pool a un altro archivio di monitoraggio. Tenere presente che, anche se non è più presente un ruolo di monitoraggio del server, sarà comunque necessario creare uno o più archivi di monitoraggio: i database back-end usati per archiviare i dati raccolti dal servizio di monitoraggio. Questi database back-end possono essere creati con Microsoft SQL Server 2008 R2, Microsoft SQL Server 2012. o Microsoft SQL Server 2014.

> [!NOTE]
> Se il monitoraggio è stato abilitato per un pool, è possibile disabilitare il processo di raccolta dei dati di monitoraggio senza dover modificare la topologia: Skype for Business Server offre la possibilità di disabilitare (e quindi riabilitare) la registrazione dei dettagli delle chiamate (CDR) o la qualità di Raccolta di dati Experience (QoE). Per altre informazioni, vedere la sezione configurazione della registrazione dei dettagli delle chiamate e della qualità delle impostazioni dell'esperienza di questo documento.

Un altro importante miglioramento per il monitoraggio in Skype for Business Server è il fatto che i report di monitoraggio di Skype for Business Server ora supportano IPv6: i report che usano il campo indirizzo IP visualizzeranno gli indirizzi IPv4 o IPv6 in base a: 1) la query SQL in uso; e 2) dove l'indirizzo IPv6 viene archiviato o meno nel database di monitoraggio.

> [!NOTE]
> Verificare che il tipo di avvio del servizio di SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza SQL che tiene i database di monitoraggio, in modo che i processi di manutenzione di SQL Server di monitoraggio predefiniti possano essere eseguiti nella loro base pianificata sotto il controllo del servizio agente SQL Server.

Questa documentazione illustra il processo di installazione e configurazione dei report di monitoraggio e monitoraggio per Skype for Business Server. La documentazione include istruzioni dettagliate che ti aiuteranno a:

- Abilitare il monitoraggio nella topologia e associare un archivio di monitoraggio a un pool Front-end.

- Installare SQL Server Reporting Services e i report di monitoraggio di Skype for Business Server. I report di monitoraggio sono report preconfigurati che contengono visualizzazioni diverse delle informazioni archiviate in un database di monitoraggio.

- Configurare la raccolta di dati per la registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE). La registrazione dei dettagli delle chiamate consente di tenere traccia dell'uso delle funzionalità di Skype for Business Server, come le chiamate telefoniche VoIP (Voice over IP); messaggistica istantanea (IM); trasferimenti di file; Servizi di conferenza audio/video (A/V); e sessioni di condivisione applicazioni. Le metriche QoE tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, inclusi i problemi relativi al numero di pacchetti di rete persi, al rumore di fondo e alla quantità di "jitter" (differenze nel ritardo del pacchetto).

- Eliminare manualmente i record CDR e/o QoE dal database di monitoraggio.

## <a name="deployment-checklist-for-monitoring"></a>Elenco di controllo di distribuzione per il monitoraggio

Anche se il monitoraggio è già installato e attivato in ogni server front-end, è necessario intraprendere diversi passaggi prima di poter effettivamente raccogliere dati di monitoraggio per Skype for Business Server. Questi passaggi sono descritti nell'elenco di controllo seguente:

|**Fase**|**Passaggi**|**Appartenenza a ruoli e gruppi**|**Documentazione**|
|:-----|:-----|:-----|:-----|
|**Installare hardware e software prerequisiti** <br/> |Installare una versione supportata di Microsoft SQL Server nel computer che fungerà da archivio dati back-end per il monitoraggio.  <br/> |Utente del dominio che è anche membro del gruppo Administrators locale.  <br/> |[Hardware supportato](https://technet.microsoft.com/library/5f9c085d-205e-4235-9061-9ad875283cb0.aspx) <br/> [Supporto per software e infrastruttura server](https://technet.microsoft.com/library/4ee5fe38-0191-4710-9aa2-df8895e8c51b.aspx) <br/> |
|**Creare la topologia interna appropriata per supportare il monitoraggio** <br/> |USA generatore di topologia di Skype for Business Server per aggiungere database di monitoraggio alla topologia, quindi pubblicato la topologia aggiornata.  <br/> |Per definire una topologia, un utente membro del gruppo utenti locali.  <br/> Per pubblicare la topologia, un utente membro se il gruppo Domain Administrators e il gruppo RTCUniversalServerAdmins.  <br/> |[Associare un archivio di monitoraggio a un pool di front-end in Skype for Business Server](associate-a-monitoring-store.md) <br/> |
|**Abilitare le impostazioni di monitoraggio appropriate** <br/> |Abilitare il monitoraggio della registrazione dei dettagli delle chiamate (CDR) e/o la qualità dell'esperienza (QoE) negli ambiti globali e/o del sito.  <br/> |Un utente membro del gruppo RTCUniversalServerAdmins o a cui è stato assegnato un ruolo RBAC che consente di accedere ai cmdlet CsCdrConfiguration e CsQoEConfiguration.  <br/> |[Configurare la registrazione dei dettagli delle chiamate e la qualità delle impostazioni dell'esperienza in Skype for Business Server](call-detail-recording-and-qoe.md) <br/> |

## <a name="enable-monitoring"></a>Abilitare il monitoraggio

Anche se gli agenti di raccolta dati unificati vengono installati e attivati automaticamente in ogni server front-end, ciò non significa che si inizierà automaticamente a raccogliere dati di monitoraggio nel momento in cui si termina l'installazione di Skype for Business Server. È invece necessario eseguire due operazioni: è necessario associare i server front-end/pool Front-end a un database di monitoraggio ed è necessario abilitare il monitoraggio della registrazione dei dettagli delle chiamate (CDR) e/o la qualità dell'esperienza (QoE) nell'ambito globale e/o nell'ambito del sito.

Per istruzioni dettagliate sull'associazione di server front-end o pool Front-end a un database di monitoraggio, vedere l'argomento [associare un archivio di monitoraggio a un pool di front-end in Skype for Business Server](associate-a-monitoring-store.md) nella Guida alla distribuzione. Dopo aver effettuato queste associazioni e dopo la pubblicazione della nuova topologia di Skype for Business Server, non sarà ancora possibile raccogliere i dati di monitoraggio. Questo perché, per impostazione predefinita, sia la raccolta di dati CDR che QoE è disabilitata quando si installa Skype for Business Server.

Per avviare la raccolta dei dati, è necessario abilitare il monitoraggio CDR e/o QoE. (Si noti che non è necessario abilitare il monitoraggio CDR e QoE, se si preferisce, è possibile abilitare un tipo di monitoraggio lasciando l'altro tipo disabilitato). Per abilitare il monitoraggio CDR nell'ambito globale, eseguire il comando seguente dall'interno di Skype for Business Server Management Shell:

```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

In alternativa, puoi abilitare il monitoraggio CDR dall'interno del pannello di controllo di Skype for Business Server. Nel pannello di controllo di Skype for Business Server completare la procedura seguente:

1. Fare clic su **monitoraggio**.

2. Nella scheda **registrazione dettagli chiamata** fare doppio clic sull'impostazione **globale** .

3. Nel riquadro **Impostazioni registrazione dettagli chiamata (CDR)** selezionare **Abilita monitoraggio di CDRS** e quindi fare clic su **commit**.

Per abilitare il monitoraggio QoE nell'ambito globale, eseguire questo comando dall'interno di Skype for Business Server Management Shell:

```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $True
```

Se si preferisce, è anche possibile abilitare il monitoraggio QoE dall'interno del pannello di controllo di Skype for Business Server. Nel pannello di controllo completare la procedura seguente:

1. Fare clic su **monitoraggio**.

2. Nella scheda **qualità di dati esperienza** fare doppio clic sull'impostazione **globale** .

3. Nel riquadro **Impostazioni modifica qualità dell'esperienza (QoE)** selezionare Abilita il **monitoraggio dei dati QoE** e quindi fare clic su **commit**.

Come indicato, gli esempi precedenti consentono il monitoraggio nell'ambito globale; in altre altre, abilitano il monitoraggio CDR e QoE in tutta l'organizzazione. In alternativa, è possibile creare impostazioni di configurazione CDR e QoE separate nell'ambito del sito e quindi abilitare o disabilitare il monitoraggio in modo selettivo per ogni sito. Ad esempio, è possibile abilitare il monitoraggio CDR per il sito Redmond, ma disabilitare il monitoraggio CDR per il sito di Dublino. Per altre informazioni sulla gestione delle impostazioni di configurazione del monitoraggio, vedere l'argomento Guida alla distribuzione [configurare la registrazione dei dettagli delle chiamate e la qualità delle impostazioni dell'esperienza in Skype for Business Server](call-detail-recording-and-qoe.md).

## <a name="see-also"></a>Vedere anche

[Pianificare il monitoraggio in Skype for Business Server](../../plan-your-deployment/monitoring.md)
