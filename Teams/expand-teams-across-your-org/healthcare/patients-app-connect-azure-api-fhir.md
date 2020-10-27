---
title: Connettere l'app Pazienti all'API di Azure per FHIR
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come connettere l'app patients in Microsoft Teams a Azure API per FHIR (Fast Healthcare Resources).
ms.openlocfilehash: 1f137f7cbe90304620bb0fc5c919c0861fca9d7e
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766989"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Connettere l'app Pazienti all'API di Azure per FHIR

> [!IMPORTANT]
> **Efficace il 30 ottobre 2020 l'app patients sarà deprecata e gli utenti non potranno più installarla dall'app teams Store. Ti invitiamo a iniziare a usare l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in teams Today.**
>
>I dati dell'app patients sono archiviati nella cassetta postale del gruppo del gruppo Office 365 che appoggia il team. Quando l'app patients viene ritirata, tutti i dati associati verranno mantenuti in questo gruppo, ma non sarà più possibile accedervi tramite l'interfaccia utente. Gli utenti correnti possono ricreare gli elenchi usando l' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>L' [app elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) è preinstallata per tutti gli utenti di teams ed è disponibile come scheda in ogni team e canale. Con gli elenchi, i team di integrità possono creare elenchi di pazienti usando il modello di pazienti incorporati, da zero o importando dati in Excel. Per ulteriori informazioni su come gestire l'app elenchi nell'organizzazione, vedere [gestire l'app elenchi](../../manage-lists-app.md).

Seguire questa procedura per consentire all'app pazienti in Microsoft teams di accedere a un'API di Azure per l'istanza di FHIR. In questo articolo si presuppone che sia stata configurata un' [API Azure per l'istanza di FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) e la configurazione del tenant.  Se non è ancora stata creata un'API Azure per l'istanza di FHIR nel tenant, vedere [Guida introduttiva: distribuire Azure API per FHIR con Azure Portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).


1. Fare clic [qui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) per concedere il consenso dell'amministratore per l'app pazienti. Quando richiesto, accedere con l'amministratore del tenant o le credenziali di amministratore globale e quindi fare clic su **accetta** per concedere le autorizzazioni necessarie.

    ![Screenshot della richiesta di autorizzazione per i pazienti app](../../media/patients-app-permissions-request.png)

    Dopo aver accettato, chiudere la finestra. Verrà visualizzata una pagina che può avere un aspetto simile al seguente. È possibile ignorare il messaggio di errore nella pagina. È innocuo e indica che viene concesso il consenso. Stiamo lavorando a una pagina più user-friendly per questo URL. Restate sintonizzati!)

    ![Screenshot della richiesta di autorizzazione per i pazienti app](../../media/patients-app-permissions-request-granted.png)
    
2. Accedere a [Azure Portal](https://portal.azure.com) con le credenziali di amministratore.

3. Nella barra di spostamento sinistra selezionare **Azure Active Directory** e quindi selezionare **applicazioni aziendali** .

    Cercare una riga denominata **patients (dev)** e quindi copiare il valore nella colonna **ID oggetto** negli Appunti.
    
    ![Screenshot della riga dei pazienti (dev) in Azure Portal](../../media/patients-app-azure-portal-object-id.png)
    
4. Passare all'istanza di risorsa Azure API for FHIR a cui si vuole connettere l'app patients, cercandola o sfogliando le risorse, quindi aprire le impostazioni per l'istanza.

    ![Screenshot dell'API Azure per le impostazioni delle istanze di FHIR in Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Fare clic su **autenticazione** e quindi incollare l'ID oggetto copiato nel passaggio 3 nella casella **ID oggetto consentiti** . Questo consente all'app patients di accedere al server FHIR. Dopo aver incollato l'ID oggetto, Azure Active Directory la convalida e viene visualizzato un segno di spunta verde accanto.

    ![Screenshot delle impostazioni di autenticazione in Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. Fare clic su **Salva** . Verrà ridistribuita l'istanza, che può richiedere alcuni minuti.

7. Fare clic su **Panoramica** e quindi copiare l'URL dall' **endpoint di metadati FHIR** . Rimuovere il tag Metadata per ottenere l'URL del server FHIR. Ad esempio, https://test02-teamshealth.azurehealthcareapis.com/ . 

    ![Screenshot dell'endpoint di metadati in Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. In teams passare all'istanza dell'app patients caricata nel team, fare clic su **Impostazioni** e quindi nella casella **collegamento** immettere l'URL dell'endpoint del server FHIR. Fare quindi clic su **Connetti** per stabilire una connessione e cercare e aggiungere i pazienti all'elenco.  

    ![Screenshot delle impostazioni dell'app patients in teams](../../media/patients-app-teams.png)
    
    Se viene visualizzato un messaggio di errore durante la connessione ai team durante questo passaggio, inviare una schermata dettagliata dell'errore, i registri di [Fiddler](https://www.telerik.com/download/fiddler) e qualsiasi altra procedura di riproduzione in un messaggio di posta elettronica con una riga dell'oggetto "app pazienti-risoluzione dei problemi della modalità EMR" in [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica dell'app Pazienti](patients-app-overview.md)
- [Integrare cartelle cliniche elettroniche in Microsoft Teams](patients-app.md)
