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
description: Informazioni su come connettere l'app Pazienti di Microsoft Teams ad Azure API per FHIR (Fast Healthcare Interoperability Resources).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731154"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="f05e7-103">Connettere l'app Pazienti all'API di Azure per FHIR</span><span class="sxs-lookup"><span data-stu-id="f05e7-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="f05e7-104">A partire dal 30 ottobre 2020, l'app Pazienti è stata ritirata e sostituita [dall'app Elenchi](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span><span class="sxs-lookup"><span data-stu-id="f05e7-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="f05e7-105">I dati dell'app Pazienti vengono archiviati nella cassetta postale del gruppo di Office 365 che backup il team.</span><span class="sxs-lookup"><span data-stu-id="f05e7-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="f05e7-106">Tutti i dati associati all'app Pazienti vengono conservati in questo gruppo, ma non sono più accessibili tramite l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f05e7-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="f05e7-107">Gli utenti possono creare di nuovo i propri elenchi usando [l'app Elenchi.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="f05e7-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="f05e7-108">Con Elenchi, i team di assistenza all'interno dell'organizzazione sanitaria possono creare elenchi di pazienti per scenari che vanno da turni e riunioni interdisciplinari del team al monitoraggio generale dei pazienti.</span><span class="sxs-lookup"><span data-stu-id="f05e7-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="f05e7-109">Per iniziare, vedere il modello Pazienti in Elenchi.</span><span class="sxs-lookup"><span data-stu-id="f05e7-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="f05e7-110">Per altre informazioni su come gestire l'app Elenchi nell'organizzazione, vedere [Gestire l'app Elenchi.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="f05e7-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="f05e7-111">Seguire questa procedura per consentire all'app Pazienti di Microsoft Teams di accedere a un'istanza di Azure API per FHIR.</span><span class="sxs-lookup"><span data-stu-id="f05e7-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="f05e7-112">Questo articolo presuppone che nel tenant sia configurata e configurata un'API di Azure per l'istanza [di FHIR.](https://azure.microsoft.com/services/azure-api-for-fhir/)</span><span class="sxs-lookup"><span data-stu-id="f05e7-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="f05e7-113">Se non è ancora stata creata un'istanza di Azure API per FHIR nel tenant, vedere Avvio rapido: Distribuire [l'API di Azure per FHIR usando il portale di Azure.](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)</span><span class="sxs-lookup"><span data-stu-id="f05e7-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="f05e7-114">Fare [clic qui per](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) concedere il consenso dell'amministratore all'app Pazienti.</span><span class="sxs-lookup"><span data-stu-id="f05e7-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="f05e7-115">Quando richiesto, accedere con le credenziali di amministratore tenant  o amministratore globale e quindi fare clic su Accetta per concedere le autorizzazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="f05e7-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Screenshot della richiesta di autorizzazione per l'app Pazienti](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="f05e7-117">Dopo aver accettato, chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="f05e7-117">After you accept, close the window.</span></span> <span data-ttu-id="f05e7-118">Verrà visualizzata una pagina simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="f05e7-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="f05e7-119">È possibile ignorare il messaggio di errore nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f05e7-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="f05e7-120">È innocuo e indica che il consenso è concesso.</span><span class="sxs-lookup"><span data-stu-id="f05e7-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="f05e7-121">Stiamo lavorando a una pagina più descrittiva per questo URL.</span><span class="sxs-lookup"><span data-stu-id="f05e7-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="f05e7-122">Resta sintonizzato!)</span><span class="sxs-lookup"><span data-stu-id="f05e7-122">Stay tuned!)</span></span>

    ![Screenshot della richiesta di autorizzazione per l'app Pazienti](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="f05e7-124">Accedere al portale [di Azure con](https://portal.azure.com) le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f05e7-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="f05e7-125">Nel riquadro di spostamento sinistro selezionare **Azure Active Directory** e quindi Applicazioni **aziendali.**</span><span class="sxs-lookup"><span data-stu-id="f05e7-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="f05e7-126">Cercare una riga denominata **Pazienti (dev)** e quindi copiare il valore della colonna **ID oggetto** negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="f05e7-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Screenshot della riga Pazienti (dev) nel portale di Azure](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="f05e7-128">Passare all'istanza della risorsa Azure API per FHIR a cui si vuole connettere l'app Pazienti (cercandola o sfogliando le risorse) e quindi aprire le impostazioni per tale istanza.</span><span class="sxs-lookup"><span data-stu-id="f05e7-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Screenshot delle impostazioni dell'istanza di Azure API per FHIR nel portale di Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="f05e7-130">Fare **clic** su Autenticazione e quindi incollare l'ID oggetto copiato nel passaggio 3 nella casella **ID oggetto** consentiti.</span><span class="sxs-lookup"><span data-stu-id="f05e7-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="f05e7-131">In questo modo l'app Pazienti può accedere al server FHIR.</span><span class="sxs-lookup"><span data-stu-id="f05e7-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="f05e7-132">Dopo aver incollato l'ID oggetto, Azure Active Directory lo convalida e un segno di spunta verde appare accanto ad esso.</span><span class="sxs-lookup"><span data-stu-id="f05e7-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Screenshot delle impostazioni di autenticazione nel portale di Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="f05e7-134">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f05e7-134">Click **Save**.</span></span> <span data-ttu-id="f05e7-135">Questa operazione ridistribuisce l'istanza, che può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="f05e7-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="f05e7-136">Fare **clic su Panoramica** e quindi copiare l'URL dall'endpoint dei metadati **FHIR.**</span><span class="sxs-lookup"><span data-stu-id="f05e7-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="f05e7-137">Rimuovere il tag di metadati per ottenere l'URL del server FHIR.</span><span class="sxs-lookup"><span data-stu-id="f05e7-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="f05e7-138">Ad esempio, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="f05e7-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Endpoint dei metadati nel portale di Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="f05e7-140">In Teams passare all'istanza dell'app Pazienti caricata nel team, fare  clic su Impostazioni e quindi immettere l'URL dell'endpoint del server FHIR nella casella Collegamento.</span><span class="sxs-lookup"><span data-stu-id="f05e7-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="f05e7-141">Quindi, fare **clic su** Connetti per stabilire una connessione, cercare e aggiungere pazienti all'elenco.</span><span class="sxs-lookup"><span data-stu-id="f05e7-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="f05e7-142">Impostazioni dell'app Pazienti in Teams</span><span class="sxs-lookup"><span data-stu-id="f05e7-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="f05e7-143">Se viene visualizzato un messaggio di errore durante la connessione a Teams durante questo passaggio, inviare uno screenshot dettagliato dell'errore, i registri di [Fiddler](https://www.telerik.com/download/fiddler) e altri passaggi di riproduzione in un messaggio di posta elettronica con la riga dell'oggetto "Risoluzione dei problemi dell'app Pazienti - modalità EMR" a [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f05e7-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f05e7-144">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f05e7-144">Related topics</span></span>

- [<span data-ttu-id="f05e7-145">Panoramica dell'app Pazienti</span><span class="sxs-lookup"><span data-stu-id="f05e7-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="f05e7-146">Integrare cartelle cliniche elettroniche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f05e7-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
