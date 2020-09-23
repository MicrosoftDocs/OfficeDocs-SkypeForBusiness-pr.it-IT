---
title: Bloccare l'accesso a SharePoint per utenti specifici
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come bloccare l'accesso a SharePoint per utenti specifici
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203839"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Bloccare l'accesso a SharePoint per utenti specifici

L'applicazione di qualsiasi criterio di accesso condizionale in SharePoint in Microsoft 365 viene applicata anche ai team. Alcune organizzazioni vogliono tuttavia bloccare l'accesso ai file di SharePoint (caricare, scaricare, visualizzare, modificare, creare) ma consentire ai dipendenti di usare i client desktop, mobili e Web Teams nei dispositivi non gestiti. In base alle regole dei criteri della CA, il blocco di SharePoint porterebbe anche a bloccare teams. In questo articolo viene spiegato come aggirare questa limitazione e consentire ai dipendenti di continuare a usare teams bloccando completamente l'accesso ai file archiviati in SharePoint.

> [!Note]
> Il blocco o la limitazione dell'accesso ai dispositivi non gestiti si basa sui criteri di accesso condizionale di Azure AD. Informazioni sulle [licenze di Azure ad](https://azure.microsoft.com/pricing/details/active-directory/). Per una panoramica dell'accesso condizionale in Azure AD, vedere [accesso condizionale in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Per informazioni sui criteri di accesso di SharePoint Online consigliati, vedere [Suggerimenti per proteggere i file e i siti di SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Se si limita l'accesso nei dispositivi non gestiti, gli utenti dei dispositivi gestiti devono usare una delle [combinazioni di sistema operativo e browser supportate](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)o avranno anche accesso limitato.

È possibile bloccare o limitare l'accesso per:

- Utenti dell'organizzazione o solo di alcuni utenti o gruppi di sicurezza.

- Tutti i siti dell'organizzazione o solo alcuni siti.

Quando Access è bloccato, verrà visualizzato un messaggio di errore. Il blocco di Access consente di garantire sicurezza e proteggere i dati sicuri. Quando Access è bloccato, verrà visualizzato un messaggio di errore.

1. Aprire l'interfaccia di amministrazione di SharePoint.

2. Espandere **Policies**criteri di  >  **accesso ai**criteri.

3. Nella sezione **dispositivi non gestiti** selezionare **Blocca accesso** e selezionare **Salva**.

   ![sezione dispositivi non gestiti per i criteri](media/no-sharepoint-access1.png)

4. Aprire il portale di [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e passare a **criteri di accesso condizionale**.

    Verrà visualizzato un nuovo criterio creato da SharePoint simile a questo esempio:

    ![un nuovo criterio denominato USA restrizioni applicate dall'app per l'accesso al browser](media/no-sharepoint-access2.png)

5. Aggiornare i criteri per destinare solo utenti specifici o un gruppo.

    ![interfaccia di amministrazione di SharePoint con la sezione selezionare l'utente evidenziata.](media/no-sharepoint-access2b.png)

  > [!Note]
> L'impostazione di questo criterio consente di ridurre l'accesso al portale di amministrazione di SharePoint. È consigliabile configurare i criteri di esclusione e selezionare gli amministratori globali e di SharePoint.

6. Verificare che solo SharePoint sia selezionato come app di destinazione cloud

    ![SharePoint è selezionato come app di destinazione.](media/no-sharepoint-access3.png)

7. Aggiornare **le condizioni** per includere anche i client desktop.

    ![app per desktop e dispositivi mobili evidenziate.](media/no-sharepoint-access4.png)

8. Verificare che **l'autorizzazione di accesso** sia abilitata

    ![concedere l'accesso è abilitato.](media/no-sharepoint-access5.png)

9. Verificare che sia abilitata l' **uso delle restrizioni applicate all'app** .

10. Abilitare i criteri e selezionare **Salva**.

    ![Le restrizioni applicate all'app sono abilitate.](media/no-sharepoint-access6.png)

Per testare i criteri, è necessario disconnettersi da qualsiasi client, ad esempio l'app desktop teams o il client di sincronizzazione di OneDrive for business, e accedere di nuovo per vedere il criterio di lavoro. Se l'accesso è stato bloccato, viene visualizzato un messaggio in teams che indica che l'elemento potrebbe non esistere.

 ![Messaggio dell'elemento non trovato.](media/access-denied-sharepoint.png)

In SharePoint si riceverà un messaggio di Access denied.

![Messaggio di Access denied.](media/blocked-access-warning.png)

## <a name="related-topics"></a>Argomenti correlati

[Controllare l'accesso per i dispositivi non gestiti in SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
