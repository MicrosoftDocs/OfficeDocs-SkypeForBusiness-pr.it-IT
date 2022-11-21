---
title: Configurare ServiceNow per Teams Rooms
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Informazioni sulla configurazione di ServiceNow nel portale di gestione Teams Rooms Pro
f1keywords: ''
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
ms.openlocfilehash: 2166332df2c4ea388256d32a9dbc35a709042041
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046855"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurare ServiceNow per Teams Rooms

Questo articolo descrive i prerequisiti e i passaggi per configurare l'ambiente ServiceNow nel portale di gestione Teams Rooms Pro.

## <a name="watch-microsoft-teams-rooms-pro-management--service-now-integration"></a>Guarda: gestione Microsoft Teams Rooms Pro - Integrazione di Service Now

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ZK4B]


### <a name="teams-rooms-prerequisites"></a>Teams Rooms prerequisiti

- È necessario avere un ruolo di amministratore del servizio assegnato. Per altre informazioni, vedere [Controllo dell'accesso basato sui ruoli con gestione Microsoft Teams Rooms Pro](rooms-pro-rbac.md).

### <a name="servicenow-prerequisites"></a>Prerequisiti di ServiceNow

- Un accesso con autorizzazione di base oppure un accesso [OAuth](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) . Per altre informazioni, vedere [Creazione di credenziali](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) in ServiceNow.
- Un'istanza ServiceNow e il relativo nome host di istanza e URI API
- Ruolo di incident_manager o superiore
- Una versione software di ServiceNow che supporta Table API

## <a name="configure-your-environment"></a>Configurare l'ambiente

La configurazione dell'ambiente è altamente personalizzabile e dipenderà dalle esigenze dell'organizzazione. I passaggi seguenti illustrano come copiare la configurazione esistente in ServiceNow nel portale di gestione di Teams Rooms Pro.

1. Aprire l'istanza di ServiceNow da copiare. Quando si completa il modulo di configurazione nel portale di gestione di Teams Rooms Pro, è necessario farvi riferimento.
2. In una nuova scheda del browser passare al [portale di gestione Teams Rooms Pro](https://portal.rooms.microsoft.com/) e passare a **Impostazioni**. Quindi, seleziona **ServiceNow** nel menu di spostamento a sinistra per aprire il modulo di configurazione.
3. Selezionare un metodo di autenticazione per accedere e immettere l'URI API e l'host istanza ServiceNow.
4. Tutti gli elementi obbligatori nella colonna ServiceNow Field della sezione Mapping campi devono essere precompilati. La tabella seguente contiene ogni campo ServiceNow e il relativo campo Microsoft Teams Rooms corrispondente. Completare l'azione per ogni riga della sezione Mapping campi. Per le definizioni di ogni campo ServiceNow, vedere [ServiceNow field definitions](#servicenow-field-definitions).

| ServiceNow | Microsoft Teams Rooms campo | Azione |
| --- | --- | --- |
| short_description | Descrizione evento imprevisto | Non è necessaria alcuna azione. Il campo Teams Rooms viene riempito automaticamente. |
| Descrizione | Primo messaggio | Non è necessaria alcuna azione. Il campo Teams Rooms viene riempito automaticamente. |
| assignment_group | Gruppo di sale | Copiare il valore assignment_group nell'istanza di ServiceNow e incollarlo nel campo Valore ServiceNow nel modulo di configurazione. Se sono presenti più assignment_group, selezionare **Aggiungi gruppo di sale** per ogni valore personalizzato aggiuntivo. |
| Gravità | Anelli | Gravità è un valore personalizzato in ServiceNow. Si tratta del quarto elemento nella seconda colonna dell'istanza di ServiceNow. Copiare il valore e incollarlo nel campo ServiceNow value nel modulo di configurazione. Se hai più di un valore di gravità, seleziona **Aggiungi anello** per ogni valore personalizzato aggiuntivo. |
| Commenti (facoltativi) | Valore personalizzato* | Per aggiungere un campo commenti al modulo di configurazione, selezionare **Aggiungi** nella parte superiore della sezione di mapping dei campi. Copiare il valore del commento nell'istanza di ServiceNow e incollarlo nel campo ServiceNow nel modulo di configurazione. Assegnare un campo Sala di Microsoft Teams dal menu a discesa e copiare e incollare il valore ServiceNow. |
| stato (risolto) | Valore personalizzato* | Copiare lo stato di risoluzione dall'istanza di ServiceNow e incollarlo nel campo valore ServiceNow nel modulo di configurazione. |
| close_code | Valore personalizzato* | Nella scheda **Informazioni sulla risoluzione** dell'istanza di ServiceNow copiare il codice di chiusura e incollarlo nel campo valore ServiceNow nel modulo di configurazione. |

*Selezionare valori personalizzati dal menu a discesa

>[!NOTE]
>Se non è possibile individuare i valori personalizzati, contattare l'amministratore di ServiceNow.

Per aggiungere altri campi obbligatori alla sezione Risolvere l'evento imprevisto, selezionare **Aggiungi**.

## <a name="test-and-enable"></a>Testare e abilitare

Dopo aver completato il modulo di configurazione, selezionare **Test** nella parte inferiore della pagina. Per inviare la configurazione è necessario il test.

Una volta superato il test, seleziona **Invia** per salvare le modifiche. Quando si è pronti per abilitare ServiceNow per l'organizzazione, impostare l'interruttore **Abilitare ServiceNow?** su **Attivato**.

## <a name="servicenow-field-definitions"></a>Definizioni dei campi ServiceNow

- **short_description**: il campo descrizione breve in ServiceNow è un breve valore alfanumerico di 160 caratteri che fornisce un riepilogo dell'incidente. La descrizione breve equivale alla descrizione degli incidenti nel portale di gestione Teams Rooms Pro.

- **descrizione**: il campo della descrizione in ServiceNow è il primo valore nella cronologia delle conversazioni di un evento imprevisto ServiceNow. La descrizione equivale a Primo messaggio nel portale di gestione Teams Rooms Pro.

- **assignment_group**: il campo del gruppo di assegnazioni in ServiceNow viene usato per organizzare gli eventi imprevisti. I gruppi di assegnazioni equivalgono ai gruppi di sale nel portale di gestione Teams Rooms Pro. Per impostazione predefinita, esiste un gruppo di chat room e ne è possibile aggiungerne altri. È possibile decidere quanti gruppi sono presenti e come raggruppare gli eventi imprevisti. Ad esempio, è possibile scegliere di organizzare gli eventi imprevisti in base alla posizione.

- **gravità**: il campo di gravità in ServiceNow viene usato per organizzare gli incidenti in base alla priorità. I valori che designano la priorità sono personalizzabili. La gravità è equivalente al campo Anello nel portale di gestione Teams Rooms Pro. Per personalizzare gli anelli nel portale di gestione di Teams Rooms Pro, passare a **Aggiornamenti** nel menu di spostamento a sinistra. Passa quindi alla scheda **Anelli** e seleziona **Aggiungi anello**.

- **commenti**: Commenti è un campo facoltativo in ServiceNow usato per includere campi obbligatori personalizzati dell'istanza ServiceNow nella configurazione del portale di gestione Teams Rooms Pro. L'equivalente dei commenti è un valore personalizzato nel portale di gestione Teams Rooms Pro.

- **stato (risolto)**: il campo stato (risolto) in ServiceNow viene usato per indicare come è stato risolto un evento imprevisto ed è necessario per chiudere un evento imprevisto. Il valore dello stato (risolto) è personalizzabile. L'equivalente di stato (risolto) è un valore personalizzato nel portale di gestione di Teams Rooms Pro.

- **close_code**: una volta risolto completamente, è necessario assegnare un codice di chiusura a un evento imprevisto. Questo valore è personalizzabile in ServiceNow. L'equivalente del codice di chiusura è un valore personalizzato nel portale di gestione di Teams Rooms Pro.
