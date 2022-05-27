---
title: Microsoft Teams report sulla licenza per la protezione delle informazioni
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
description: Informazioni su come usare il report sulla licenza di Teams Information Protection nell'interfaccia di amministrazione di Microsoft Teams per vedere in che modo le app dell'organizzazione usano LE API di sottoscrizione di eventi di notifica delle modifiche.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fade7b4d5d89061cdc1dd5eb231a80d5ee9e8938
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681537"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams report sulla licenza per la protezione delle informazioni


Teams report sulle licenze di protezione delle informazioni fornisce informazioni dettagliate sull'utilizzo delle API [di Microsoft Graph API con requisiti di licenza e pagamento](/graph/teams-licenses). Questo report evidenzia tutte le app che usano queste API in [model=A](/graph/teams-licenses#modela-requirements). Non mostra l'utilizzo quando le API vengono usate in [modalità model=B](/graph/teams-licenses#modelb-requirements) o [di valutazione](/graph/teams-licenses#evaluation-mode-default-requirements). 


## <a name="view-the-information-protection-license-report"></a>Visualizzare il report sulla licenza per la protezione delle informazioni

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Analisi & report** > **Utilizzo report**. Nella scheda **Visualizza report**, in **Report**, selezionare **Information Protection Licenza**.
2. In **Intervallo di date** selezionare un intervallo.
3. In **App** seleziona un'app e quindi **esegui report**.

    ![Screenshot dell'elenco a discesa del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams con callout.](../media/teams-info-protection-license-report-dropdown-with-callouts.png "Screenshot dell'elenco a discesa del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams con callout.")

4. Per ogni categoria, possono essere visualizzate le metriche sugli utenti con licenza, gli utenti senza licenza, la capacità di seeding e la capacità utilizzata. 

    ![Screenshot del grafico di riepilogo del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams della notifica di modifica con callout.](../media/teams-info-protection-license-report-chart-with-callouts.png "Screenshot del grafico di riepilogo del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams della notifica di modifica con callout.")

5. I dati possono essere esportati facendo clic sul pulsante Esporta. È possibile passare ai dati della tabella facendo clic sulle schede per Teams modificare l'API di notifica, Teams api patch, Teams le API di esportazione (chat) e Teams esportare API (team). 

    ![Screenshot delle diverse schede del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams delle schede con callout.](../media/teams-info-protection-license-report-legend-tabs-with-callouts.png "Screenshot delle diverse schede del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams delle schede con callout.")

    ![Screenshot della scheda di notifica di modifica del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams con callout.](../media/teams-info-protection-license-report-change-notification-with-callouts.png "Screenshot della scheda di notifica di modifica del report Teams licenza per la protezione delle informazioni nell'interfaccia di amministrazione di Teams con callout.")


## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report sulla licenza per la protezione delle informazioni può essere visualizzato per le tendenze degli ultimi tre mesi. |
|**2**   |Il nome dell'app visualizzerà un elenco di tutte le app che hanno usato [Microsoft API Graph che ha requisiti di licenza e pagamento](/graph/teams-licenses) durante il periodo di tempo selezionato.|
|**3**   |Numero di utenti con [licenze](/graph/teams-licenses#required-licenses-for-modela) valide.  |
|**4**   |Numero di utenti che non hanno una [licenza](/graph/teams-licenses#required-licenses-for-modela) valida.  |
|**5**   |Volume totale chiamate API consentito a un'app oltre la quale una commissione di consumo per chiamata API verrà addebitata all'app. |
|**6**   |Volume totale chiamate API utilizzato dall'app per l'intervallo di date specificato. |
|**7**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi la scheda **Download**. Selezionare **Scarica** per scaricare il report quando è pronto. Questa esportazione esporterà solo la scheda attualmente selezionata.|
|**8**   |Selezionare un'etichetta specifica per visualizzarla o nasconderla in un grafico. |
|**9**   |Ogni scheda mostra l'uso di un particolare set di API, vale a dire [la notifica delle modifiche](/graph/api/resources/webhooks), [l'API di esportazione](/microsoftteams/export-teams-content) e [l'API di aggiornamento dei messaggi](/graph/api/message-update). Seleziona una scheda per visualizzare i dettagli di utilizzo dell'API. |
|**10**   |**Modificare l'utilizzo dell'API di notifica**<li>**Nome visualizzato** : nome visualizzato dell'utente per il quale è stata attivata una notifica di modifica.</li><li>**Licenza richiesta** : indica se l'utente ha la licenza necessaria per inviare correttamente una notifica di modifica all'app.</li><li>**Numero di tentativi** : numero totale di notifiche di modifica attivate a causa dell'utente.</li><li>**Notifica di modifica inviata** : numero totale di notifiche di modifica inviate all'app. Questa operazione sarà inferiore alle notifiche di modifica totali attivate se l'utente non ha una licenza valida.</li>|
|**11**|**Patch API**<li>**Nome visualizzato** : nome visualizzato dell'utente in cui è stato eseguito un tentativo di aggiornamento del messaggio.</li> <li>**Licenza richiesta** : indica se l'utente ha la licenza richiesta per l'aggiornamento del messaggio.</li><li>**Tentativo di conteggio** : il totale dei tentativi di aggiornamento dei messaggi.</li><li>**Messaggio con patch** : il totale dei messaggi che sono stati aggiornati correttamente.</li>|
|**12**|**Utilizzo DELL'API di esportazione chat**<li>**Nome visualizzato** : nome visualizzato dell'utente in cui è stato effettuato un tentativo di esportare il messaggio di chat dell'utente.</li><li>**Licenza richiesta** : indica se l'utente ha la licenza richiesta per l'esportazione del messaggio.</li><li>**Tentativo di conteggio** : totale dei tentativi di esportazione dei messaggi di chat.</li><li>**Messaggio esportato** - Totale tentativi in cui il messaggio di chat è stato esportato correttamente.</li> |
|**13**|**Utilizzo API esportazione team**<li>**Nome visualizzato** : nome visualizzato del team in cui è stato effettuato un tentativo di esportazione del messaggio del team.</li><li>**Numero di tentativi** : totale dei tentativi di esportazione dei messaggi del team.</li><li>**Messaggio esportato** : totale dei tentativi in cui il messaggio del team è stato esportato correttamente.</li> |


## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel Teams report attività utente, è necessario essere un amministratore globale. Le informazioni identificabili, ad esempio il nome visualizzato, la posta elettronica e l'ID Azure AD, verranno nascoste nei report e nelle relative esportazioni.

1. Nella interfaccia di amministrazione di Microsoft 365 passare a **Impostazioni** \> **org Impostazioni** e nella scheda **Servizi** scegliere **Report**.
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report sull'utilizzo nel interfaccia di amministrazione di Microsoft 365 che nell'interfaccia di amministrazione di Teams.
  
3. Selezionare **Salva modifiche**.