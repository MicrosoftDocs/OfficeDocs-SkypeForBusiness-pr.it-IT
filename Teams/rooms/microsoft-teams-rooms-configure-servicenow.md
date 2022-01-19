---
title: Configurare ServiceNow per Teams Rooms
author: cazawideh
ms.author: czawideh
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Informazioni sulla configurazione di ServiceNow nel portale Teams Rooms Premium
f1keywords: ''
ms.openlocfilehash: deca4f8111dec958b19d9a6fa2651fca34f4050f
ms.sourcegitcommit: 9caa3131e9896b140afe10edea2b1e599eacd02b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2022
ms.locfileid: "62082212"
---
# <a name="configure-servicenow-for-teams-rooms"></a>Configurare ServiceNow per Teams Rooms

Questo articolo descrive i prerequisiti e i passaggi per configurare l'ambiente ServiceNow nel Teams Rooms Premium portale.

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="teams-rooms-prerequisites"></a>Teams Rooms prerequisiti

- È necessario avere un ruolo di amministratore del servizio assegnato. Per altre informazioni, vedere [Controllo dell'accesso](microsoft-teams-rooms-premium-rbac.md)basato sui ruoli con Microsoft Teams Rooms Servizi gestiti.

### <a name="servicenow-prerequisites"></a>Prerequisiti di ServiceNow

- Un accesso autorizzazione di base o un accesso [OAuth.](https://docs.servicenow.com/bundle/rome-platform-administration/page/administer/security/concept/c_OAuthApplications.html) Per altre informazioni, vedere [Creazione di credenziali](https://developer.servicenow.com/dev.do#!/learn/learning-plans/rome/servicenow_application_developer/app_store_learnv2_rest_rome_creating_credentials) in ServiceNow.
- Un'istanza serviceNow e il relativo nome host di istanza e l'URI API
- Un ruolo di incident_manager o superiore
- Una versione software di ServiceNow che supporta Table API

## <a name="configure-your-environment"></a>Configurare l'ambiente

La configurazione dell'ambiente è altamente personalizzabile e dipende dalle esigenze dell'organizzazione. I passaggi seguenti illustrano come copiare la configurazione esistente in ServiceNow nel Teams Rooms Premium portale.

1. Aprire l'istanza di ServiceNow da copiare. È necessario fare riferimento a questa opzione quando si completa il modulo di configurazione nel Teams Rooms Premium portale.
2. In una nuova scheda del browser passare al [portale Teams Rooms Premium e](https://portal.rooms.microsoft.com/) passare a **Impostazioni**. Quindi, selezionare **ServiceNow** nel menu di spostamento sinistro per aprire il modulo di configurazione.
3. Selezionare un metodo di autenticazione per accedere e immettere l'host dell'istanza di ServiceNow e l'URI API.
4. Tutti gli elementi obbligatori nella colonna Campo ServiceNow della sezione Mapping campi devono essere precompilato. La tabella seguente contiene ogni campo ServiceNow e il campo Microsoft Teams Rooms corrispondente. Completare l'azione per ogni riga della sezione Mapping campi. Per le definizioni di ogni campo ServiceNow, vedere [Definizioni di campo ServiceNow](#servicenow-field-definitions).

| ServiceNow | Microsoft Teams Rooms campo | Azione |
| --- | --- | --- |
| short_description | Descrizione dell'incidente | Non è necessaria alcuna azione. Il Teams Rooms campo viene compilato automaticamente. |
| descrizione | Primo messaggio | Non è necessaria alcuna azione. Il Teams Rooms campo viene compilato automaticamente. |
| assignment_group | Gruppo di chat room | Copiare assignment_group valore nell'istanza di ServiceNow e incollarlo nel campo Valore ServiceNow nel modulo di configurazione. Se sono disponibili più assignment_group, selezionare Aggiungi gruppo di chat **room** per ogni valore personalizzato aggiuntivo. |
| gravità | Anelli | La gravità è un valore personalizzato in ServiceNow. Si tratta del quarto elemento nella seconda colonna dell'istanza di ServiceNow. Copiare il valore e incollarlo nel campo Valore ServiceNow nel modulo di configurazione. Se si hanno più valori di gravità, selezionare **Aggiungi anello** per ogni valore personalizzato aggiuntivo. |
| Commenti (facoltativo) | Valore personalizzato* | Per aggiungere un campo commenti al modulo di configurazione, selezionare **Aggiungi** nella parte superiore della sezione di mapping dei campi. Copiare il valore del commento nell'istanza di ServiceNow e incollarlo nel campo ServiceNow nel modulo di configurazione. Assegnare un campo Microsoft Teams room dal menu a discesa e copiare e incollare il valore ServiceNow. |
| stato (risolto) | Valore personalizzato* | Copiare lo stato di risoluzione dall'istanza di ServiceNow e incollarlo nel campo valore ServiceNow nel modulo di configurazione. |
| close_code | Valore personalizzato* | Nella scheda **Informazioni risoluzione** dell'istanza di ServiceNow copiare il codice di chiusura e incollarlo nel campo del valore ServiceNow nel modulo di configurazione. |

*Selezionare valori personalizzati dal menu a discesa

>[!NOTE]
>Se non è possibile trovare i valori personalizzati, contattare l'amministratore di ServiceNow.

Per aggiungere altri campi obbligatori alla sezione Risolvi evento imprevisto, selezionare **Aggiungi**.

## <a name="test-and-enable"></a>Testare e abilitare

Dopo aver completato il modulo di configurazione, selezionare **Test** nella parte inferiore della pagina. I test sono necessari per inviare la configurazione.

Dopo aver superato correttamente il test, selezionare **Invia** per salvare le modifiche. Quando si è pronti per abilitare ServiceNow per l'organizzazione, impostare l'interruttore Vuoi abilitare **ServiceNow?** su **Attivato.**

## <a name="servicenow-field-definitions"></a>Definizioni dei campi ServiceNow

- **short_description:** il breve campo di descrizione in ServiceNow è un breve valore alfanumerico di 160 caratteri che fornisce un riepilogo dell'incidente. Una breve descrizione equivale alla descrizione dell'incidente nel Teams Rooms Premium portale.

- **descrizione:** il campo di descrizione in ServiceNow è il primo valore nella cronologia delle conversazioni di un evento serviceNow. Descrizione equivale a Primo messaggio nel Teams Rooms Premium portale.

- **assignment_group:** il campo del gruppo di assegnazioni in ServiceNow viene usato per organizzare gli eventi imprevisti. I gruppi di attività sono equivalenti ai gruppi di chat room nel Teams Rooms Premium portale. Per impostazione predefinita, è presente un gruppo di chat room e ne è possibile aggiungere altri. È possibile decidere quanti gruppi sono presenti e come raggruppare gli eventi imprevisti. Ad esempio, è possibile scegliere di organizzare gli eventi imprevisti in base alla posizione.

- **severity:** il campo severity in ServiceNow viene usato per organizzare gli incidenti in base alla priorità. I valori che designano la priorità sono personalizzabili. La gravità equivale al campo Anello nel portale Teams Rooms Premium. Per personalizzare gli anelli nel portale Teams Rooms Premium, passare **a Aggiornamenti** nel menu di spostamento sinistro. Passare quindi alla **scheda Anelli** e selezionare **Aggiungi anello.**

- **commenti:** i commenti sono un campo facoltativo in ServiceNow usato per includere i campi obbligatori personalizzati dell'istanza di ServiceNow nella configurazione Teams Rooms Premium portale. L'equivalente dei commenti è un valore personalizzato nel Teams Rooms Premium portale.

- **stato (risolto):** il campo stato (risolto) in ServiceNow viene usato per designare la modalità di risoluzione di un evento imprevisto ed è necessario per chiudere un evento imprevisto. Il valore stato (risolto) è personalizzabile. L'equivalente dello stato (risolto) è un valore personalizzato nel Teams Rooms Premium portale.

- **close_code**: è necessario assegnare un codice di chiusura a un evento imprevisto dopo la risoluzione completa. Questo valore è personalizzabile in ServiceNow. L'equivalente del codice di chiusura è un valore personalizzato nel Teams Rooms Premium portale.
