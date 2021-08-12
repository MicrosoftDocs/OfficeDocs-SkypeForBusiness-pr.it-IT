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
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Informazioni su come usare il report sulle licenze di Teams information protection nell'interfaccia di amministrazione di Microsoft Teams per vedere come le app dell'organizzazione usano le API di sottoscrizione degli eventi di notifica delle modifiche.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ea5916cdf2d91a8440f5b674b1dc60ceb29f804dd5b547d1867ffaad69af8d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308337"
---
# <a name="microsoft-teams-information-protection-license-report"></a>Microsoft Teams di licenza per la protezione delle informazioni

Il report sulle licenze di protezione delle informazioni [](/graph/api/resources/subscription?view=graph-rest-1.0) di [](/graph/api/resources/webhooks?view=graph-rest-1.0) Teams fornisce informazioni approfondite sulle app che hanno sottoscritto la modifica degli eventi di notifica per ascoltare i messaggi creati, aggiornati o eliminati a livello di tenant, ovvero /teams/getAllMessage o /chats/getAllMessages. Una notifica di modifica corrispondente al messaggio viene inviata correttamente solo quando l'utente ha la [licenza richiesta.](/graph/teams-licenses)  È possibile visualizzare il numero di notifiche di modifica attivate da un determinato utente.


## <a name="view-the-information-protection-license-report"></a>Visualizzare il report sulle licenze di protezione delle informazioni

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](../using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione selezionare Analisi **& report**  >  **utilizzo**. Nella scheda **Visualizza report,** in **Report,** selezionare **Licenza di protezione delle informazioni.**
2. In **Intervallo di date** selezionare un intervallo.
3. In **App** selezionare un'app e quindi **selezionare Esegui report.**

    ![Screenshot del report Teams di licenza per la protezione delle informazioni nell'Teams di amministrazione con callout](../media/teams-info-protection-license-report-with-callouts.png "Screenshot del report Teams di licenza per la protezione delle informazioni nell'Teams di amministrazione con callout")

## <a name="interpret-the-report"></a>Interpretare il report

|Callout |Descrizione  |
|--------|-------------|
|**1**   |Il report sulle licenze di protezione delle informazioni può essere visualizzato per le tendenze degli ultimi 7, 30 o 90 giorni. |
|**2**   |Il nome dell'app visualizza un elenco di tutte le app che hanno sottoscritto la sottoscrizione per modificare gli eventi di notifica dei messaggi negli ultimi n giorni come selezionato nell'intervallo di date. |
|**3**   |La tabella fornisce una suddivisione dell'utilizzo per utente per l'app selezionata.<ul><li>**Nome visualizzato** è il nome visualizzato dell'utente. Selezionare il nome visualizzato per passare alla pagina dei dettagli dell'utente nell'Microsoft Teams di amministrazione.</li><li>**Has Required License** è sì se l'utente ha una delle licenze richieste come definito (qui)[ https://docs.microsoft.com/en-us/graph/teams-licenses ]. Se l'utente non ha la  licenza richiesta, viene visualizzato il collegamento Assegna licenza che consente di passare alla pagina dei dettagli della licenza dell'utente nell'interfaccia di amministrazione Microsoft (**Utenti** utenti attivi > seleziona nome  >   utente).</li><li>**Eventi protetti da licenza** è il numero di eventi di notifica delle modifiche univoci inviati all'app a fronte di un messaggio creato, aggiornato o eliminato dall'utente.</li></ul> |
|**4**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi la **scheda** Download. Selezionare **Scarica** per scaricare il report quando è pronto. |
|**5**   |Esportare il report in un file CSV per l'analisi offline. Selezionare **Esporta in Excel** e quindi la **scheda** Download. Selezionare **Scarica** per scaricare il report quando è pronto. Quando si visualizza il report in Excel, viene visualizzata  anche una colonna **ID** e un messaggio di posta elettronica, che rappresenta l'ID utente e l'indirizzo di posta elettronica dell'utente. |

## <a name="make-the-user-specific-data-anonymous"></a>Rendere anonimi i dati specifici dell'utente

Per rendere anonimi i dati nel report Teams utente, è necessario essere un amministratore globale. In questo modo si nasconderanno informazioni identificabili come il nome visualizzato, la posta elettronica e l'ID di Azure AD nei report e nelle relative esportazioni.

1. Nella finestra interfaccia di amministrazione di Microsoft 365, passare  a Impostazioni org Impostazioni e nella scheda Servizi \> scegliere **Report.** 
    
2. Selezionare **Report** e quindi scegliere **Visualizza identificatori anonimi**. Questa impostazione viene applicata sia ai report di utilizzo nell'interfaccia di amministrazione di Microsoft 365 e nell'Teams di amministrazione.
  
3. Selezionare **Salva modifiche**.
