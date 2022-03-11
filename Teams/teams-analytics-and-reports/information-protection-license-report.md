---
title: Microsoft Teams di licenza per la protezione delle informazioni
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sulle licenze di Teams information protection nell'interfaccia di amministrazione di Microsoft Teams per vedere come le app dell'organizzazione usano le API di sottoscrizione degli eventi di notifica delle modifiche.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73ce4b5720c42cdb4e468182d6290912baf95d7e
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435860"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams di licenza per la protezione delle informazioni


Teams report sulle licenze per la protezione delle informazioni fornisce informazioni sull'utilizzo delle API [Microsoft Graph che hanno requisiti di licenza e pagamento](/graph/teams-licenses). Questo report evidenzia tutte le app che usano queste API in [model=A](/graph/teams-licenses#modela-requirements). Non mostra l'uso quando le API vengono usate in [model=B o](/graph/teams-licenses#modelb-requirements) in [modalità di valutazione](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Visualizzare il report sulle licenze di protezione delle informazioni

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione selezionare **Analisi &** **reportUsage** > . Nella scheda **Visualizza report** , in **Report**, selezionare **Licenza di protezione delle informazioni**.
2. In **Intervallo di date** selezionare un intervallo.
3. In **App** selezionare un'app e quindi **selezionare Esegui report**.

    ![Screenshot dell'elenco a discesa Teams report sulla licenza di protezione delle informazioni nell'Teams di amministrazione con callout.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Screenshot dell'elenco a discesa Teams report sulla licenza di protezione delle informazioni nell'Teams di amministrazione con callout.")

4. Per ogni categoria, è possibile visualizzare le metriche relative agli utenti con licenza, agli utenti senza licenza, alla capacità di seeded e alla capacità utilizzata. 

    ![Screenshot del grafico di riepilogo del report Teams sulla licenza di protezione delle informazioni nell'Teams di amministrazione della notifica di modifica con callout.](../media/teams-info-protection-license-report-chart-with-callouts.png "Screenshot del grafico di riepilogo del report Teams sulla licenza di protezione delle informazioni nell'Teams di amministrazione della notifica di modifica con callout.")

5. I dati possono essere esportati facendo clic sul pulsante Esporta. È possibile cambiare i dati della tabella facendo clic sulle schede per l'API di notifica delle modifiche di Teams, l'API di patch di Teams, le API di esportazione Teams (chat) e le API di Teams di esportazione (teams). 

    ![Screenshot delle diverse schede del report Teams di licenza di protezione delle informazioni nell'Teams di amministrazione delle schede con callout.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Screenshot delle diverse schede del report Teams di licenza di protezione delle informazioni nell'Teams di amministrazione delle schede con callout.")

    ![Screenshot della scheda notifica di modifica Teams report sulla licenza di protezione delle informazioni nell'Teams di amministrazione con callout.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Screenshot della scheda notifica di modifica Teams report sulla licenza di protezione delle informazioni nell'Teams di amministrazione con callout.")


## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report sulle licenze di protezione delle informazioni può essere visualizzato per le tendenze degli ultimi tre mesi. |
|**2**   |Il nome dell'app visualizza un elenco di tutte le app che hanno usato [l'API microsoft Graph che](/graph/teams-licenses) ha requisiti di licenza e pagamento durante il periodo di tempo selezionato.|
|**3**   |Numero di utenti con licenze [valide](/graph/teams-licenses#required-licenses-for-modela).  |
|**4**   |Numero di utenti che non hanno una licenza [valida](/graph/teams-licenses#required-licenses-for-modela).  |
|**5**   |Volume totale di chiamate API consentito a un'app oltre la quale all'app verrà addebitata una tariffa di consumo per ogni chiamata API. |
|**6**   |Volume totale delle chiamate API usate dall'app per l'intervallo di date specificato. |
|**7**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi la **scheda Download**. Selezionare **Scarica** per scaricare il report quando è pronto. Questa esportazione esporterà solo la scheda attualmente selezionata.|
|**8**   |Selezionare un'etichetta specifica per mostrarla o nasconderla in un grafico. |
|**9**   |Ogni scheda visualizza l'uso di un particolare set di API, ad esempio la notifica di [modifica,](/graph/api/resources/webhooks) [l'API](/microsoftteams/export-teams-content) di esportazione e [l'API dei messaggi di aggiornamento](/graph/api/message-update). Selezionare una scheda per visualizzare i dettagli sull'utilizzo dell'API. |
|**10**   |**Modificare l'utilizzo dell'API di notifica**<li>**Nome visualizzato** : nome visualizzato dell'utente in base al quale è stata attivata una notifica di modifica.</li><li>**Licenza richiesta: indica** se l'utente specificato ha la licenza necessaria per inviare correttamente una notifica di modifica all'app.</li><li>**Numero tentativi** : numero totale di notifiche di modifica che sono state attivate a causa di questo utente.</li><li>**Notifica di modifica inviata** : numero totale di notifiche di modifica inviate all'app. Sarà minore delle notifiche di modifica totali attivate se l'utente non ha una licenza valida.</li>|
|**11**|**Patch API**<li>**Nome visualizzato** : nome visualizzato dell'utente in cui è stato eseguito un tentativo di aggiornamento del messaggio.</li> <li>**Licenza richiesta** : indica se l'utente specificato ha la licenza necessaria per il corretto aggiornamento del messaggio.</li><li>**Numero tentativi** : totale dei tentativi di aggiornamento dei messaggi.</li><li>**Message Patched** : numero totale di messaggi aggiornati correttamente.</li>|
|**12**|**Utilizzo dell'API di esportazione chat**<li>**Nome visualizzato** : nome visualizzato dell'utente in cui è stato eseguito un tentativo di esportare il messaggio di chat dell'utente.</li><li>**Licenza richiesta** : indica se l'utente specificato ha la licenza necessaria per esportare correttamente il messaggio.</li><li>**Numero tentativi** : numero totale di tentativi di esportazione dei messaggi di chat.</li><li>**Messaggio esportato** - Totale dei tentativi in cui il messaggio di chat è stato esportato correttamente.</li> |
|**13**|**Utilizzo dell'API di esportazione del team**<li>**Nome visualizzato** : nome visualizzato del team in cui è stato eseguito un tentativo di esportare il messaggio del team.</li><li>**Numero tentativi** : totale dei tentativi di esportazione dei messaggi del team.</li><li>**Messaggio esportato** : totale dei tentativi in cui il messaggio del team è stato esportato correttamente.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report Teams utente, è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili, ad esempio nome visualizzato, posta elettronica e ID Azure AD nei report e nelle relative esportazioni.

1. Nella finestra interfaccia di amministrazione di Microsoft 365, **passare a** \> Impostazioni **org Impostazioni** e nella scheda Servizi scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo nell'interfaccia di amministrazione di Microsoft 365 che nell'Teams di amministrazione.
  
3. Selezionare **Salva modifiche**.