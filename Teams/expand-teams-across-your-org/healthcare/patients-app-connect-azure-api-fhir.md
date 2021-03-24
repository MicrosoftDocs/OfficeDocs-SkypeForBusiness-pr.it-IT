---
title: Connettere l'app Pazienti all'API di Azure per FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Informazioni su come connettere l'app Pazienti in Microsoft Teams ad Azure API for FHIR (Fast Healthcare Interoperability Resources).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096268"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Connettere l'app Pazienti all'API di Azure per FHIR

> [!NOTE]
> A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita dall’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams. I dati dell’app Pazienti vengono archiviati nella casella postale di gruppo del gruppo di Office 365 che supporta il team. Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non è più possibile accedervi tramite l'interfaccia utente. Gli utenti possono ricreare i propri elenchi utilizzando l’app [Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Elenchi, i team di assistenza della tua organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni di team interdisciplinari al monitoraggio generale dei pazienti. Estrai il modello Coordinamento pazienti in Elenchi per iniziare. Per ulteriori informazioni su come gestire l'app Elenchi nella tua organizzazione, vedere [Gestire l’app Elenchi](../../manage-lists-app.md).

Seguire questa procedura per consentire all'app Pazienti in Microsoft Teams di accedere a un'istanza di Azure API per FHIR. Questo articolo presuppone che nel tenant sia configurata e configurata un'istanza di Azure API per [FHIR.](https://azure.microsoft.com/services/azure-api-for-fhir/)  Se non è ancora stata creata un'istanza di Azure API per FHIR nel tenant, vedere Guida introduttiva: Distribuire l'API di Azure per [FHIR usando il portale di Azure.](/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. Fare [clic qui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) per concedere il consenso dell'amministratore per l'app Pazienti. Quando richiesto, accedere con le credenziali di amministratore tenant o amministratore globale e quindi fare clic **su** Accetta per concedere le autorizzazioni necessarie.

    ![Screenshot della richiesta di autorizzazione per l'app Pazienti](../../media/patients-app-permissions-request.png)

    Dopo aver accettato, chiudere la finestra. Verrà visualizzata una pagina simile alla seguente. È possibile ignorare il messaggio di errore nella pagina. È innocuo e indica che il consenso è concesso. Stiamo lavorando a una pagina più facile da usare per questo URL. Rimani sintonizzato!)

    ![Screenshot della richiesta di autorizzazione per l'app Patients](../../media/patients-app-permissions-request-granted.png)

2. Accedere al portale [di Azure con](https://portal.azure.com) le credenziali di amministratore.

3. Nel riquadro di spostamento sinistro selezionare **Azure Active Directory** e quindi applicazioni **aziendali.**

    Cercare una riga denominata **Pazienti (dev)** e quindi copiare il valore nella **colonna ID oggetto** negli Appunti.

    ![Screenshot della riga Pazienti (dev) nel portale di Azure](../../media/patients-app-azure-portal-object-id.png)

4. Passare all'istanza della risorsa API di Azure per FHIR a cui si vuole connettere l'app Pazienti (cercandola o esplorando le risorse) e quindi aprire le impostazioni per tale istanza.

    ![Screenshot delle impostazioni dell'istanza di Azure API per FHIR nel portale di Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. Fare **clic su** Autenticazione e quindi incollare l'ID oggetto copiato nel passaggio 3 nella casella ID **oggetto** consentiti. In questo modo l'app Pazienti può accedere al server FHIR. Dopo aver incollato l'ID oggetto, Azure Active Directory lo convalida e accanto viene visualizzato un segno di spunta verde.

    ![Screenshot delle impostazioni di autenticazione nel portale di Azure](../../media/patients-app-azure-portal-authentication.png)

6. Fare clic su **Salva**. Questa operazione ridistribuisce l'istanza, che può richiedere alcuni minuti.

7. Fare **clic su Panoramica** e quindi copiare l'URL dall'endpoint dei metadati **FHIR.** Rimuovere il tag di metadati per ottenere l'URL del server FHIR. Ad esempio, `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![endpoint dei metadati nel portale di Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. In Teams passare all'istanza dell'app Pazienti caricata nel team, fare  clic su Impostazioni **e** quindi nella casella Collegamento immettere l'URL dell'endpoint del server FHIR. Quindi, fare clic **su Connetti** per stabilire una connessione e cercare e aggiungere pazienti all'elenco.  

    ![ Impostazioni dell'app Pazienti in Teams](../../media/patients-app-teams.png)

    Se durante questo passaggio viene visualizzato un messaggio di errore durante la connessione a Teams, inviare a teamsforhealthcare@service.microsoft.com uno screenshot dettagliato dell'errore, i log di [Fiddler](https://www.telerik.com/download/fiddler) e qualsiasi altro processo di riproduzione in un messaggio di posta elettronica con l'oggetto "Risoluzione dei problemi relativi all'app Pazienti – modalità [EMR"](mailto:teamsforhealthcare@service.microsoft.com)in teamsforhealthcare@service.microsoft.com .

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica dell'app Pazienti](patients-app-overview.md)
- [Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)