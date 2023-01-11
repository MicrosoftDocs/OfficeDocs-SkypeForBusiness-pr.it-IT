---
title: Gestire gli account delle risorse in Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: In questo articolo imparerai a creare, modificare e gestire gli account delle risorse in Microsoft Teams.
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763577"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gestire gli account di risorsa in Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Passaggi successivi

Dopo aver completato la configurazione dell'account delle risorse e aver assegnato un numero di telefono, se necessario, sei pronto per usare l'account della risorsa con un operatore automatico o una coda di chiamata.

Per altre informazioni, vedere i riferimenti seguenti:

- [Operatore automatico cloud](create-a-phone-system-auto-attendant.md)
- [Coda di chiamata cloud](create-a-phone-system-call-queue.md)

È possibile modificare l'account della risorsa **Nome visualizzato** e tipo di **account risorsa** usando l'opzione **Modifica** . Al termine, seleziona **Salva** .

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modificare un account di risorse esistente per usare una licenza Telefono di Microsoft Teams Account risorse

Per cambiare le licenze dell'account delle risorse esistente da una licenza **di Teams Phone Standard** a una Telefono di Microsoft Teams licenza **Account risorse**, è necessario acquisire la licenza **Telefono di Microsoft Teams Account risorse** e quindi seguire la procedura descritta in interfaccia di amministrazione di Microsoft 365 [spostare gli utenti in un abbonamento diverso](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Rimuovere sempre una licenza **di Teams Phone Standard** e assegnare la licenza **Telefono di Microsoft Teams Account risorse** nella stessa attività di licenza. Se si rimuove la licenza precedente, si salvano le modifiche dell'account, si aggiunge la nuova licenza e quindi si salvano di nuovo le impostazioni dell'account, l'account della risorsa potrebbe non funzionare più come previsto. In questo caso, è consigliabile creare un nuovo account per le risorse per la licenza **Account risorse di Telefono di Microsoft Teams** e rimuovere l'account delle risorse danneggiato.

## <a name="skype-for-business-server-2019"></a>Skype for Business Server 2019

Per gli account di risorse ospitati su Skype For Business Server 2019 che possono essere utilizzati con code di chiamata cloud e operatori automatici cloud, consulta [Pianificare code di chiamata cloud](/SkypeforBusiness/hybrid/plan-call-queue) o [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Le implementazioni ibride (numeri ospitati nel routing diretto) vengono configurate utilizzando il cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) in un server locale Skype for Business Server 2019.

Gli ID applicazione che è necessario usare durante la creazione delle istanze dell'applicazione sono:

- **Operatore automatico:** ce933385-9390-45d1-9512-c8d228074e07
- **Coda di chiamata:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Se desideri che la coda di chiamata o l'operatore automatico sia disponibile per la ricerca da parte degli utenti di Skype For Business Server 2019, devi creare i tuoi account di risorse su Skype For Business Server 2019, poiché gli account delle risorse online non vengono sincronizzati con Active Directory. Quando i record SRV DNS per sipfederationtls vengono risolti in Skype for Business Server 2019, gli account delle risorse **devono** essere creati in Skype For Business Server 2019 utilizzando sfB Management shell e sincronizzati con Azure AD.

Per le implementazioni ibride con Skype for Business Server:

- [Pianificare gli operatori automatici cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).
- [Pianificare le code di chiamata cloud](/SkypeforBusiness/hybrid/plan-call-queue).
- [Configurare gli account delle risorse locali](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="delete-a-resource-account"></a>Eliminare un account di risorsa

Assicurarsi di dissociare il numero di telefono dall'account della risorsa prima di eliminarlo, per evitare che il numero di telefono rimanga bloccato in modalità in sospeso.

Dopo aver eseguito questa operazione, è possibile eliminare l'account della risorsa nel interfaccia di amministrazione di Microsoft 365, nella scheda **Utenti**.

Per rimuovere l'associazione da un numero di telefono direct routing dall'account della risorsa, usare il cmdlet seguente:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>Nascondere gli account delle risorse agli utenti di Teams

È consigliabile nascondere determinati account di risorse agli utenti di Teams. Ad esempio, è consigliabile impedire agli utenti di Teams di chiamare direttamente una coda di chiamata e di ignorare l'operatore automatico in cui sono configurate le ore di funzionamento.

[Gli ostacoli alle informazioni](information-barriers-in-teams.md) vengono usati per nascondere gli account delle risorse.  Esaminare la documentazione sugli ostacoli alle informazioni per comprendere i possibili impatti prima di procedere con la procedura seguente.

### <a name="required-subscriptions-and-permissions"></a>Abbonamenti e autorizzazioni necessari 

Per accedere e usare le barriere informative, l'organizzazione deve avere uno degli abbonamenti o componenti aggiuntivi seguenti: 

-   abbonamento Microsoft 365 E5/A5 (versione di valutazione o a pagamento).
-   abbonamento Office 365 E5/A5/A3/A1 (versione di valutazione o a pagamento).
-   Office 365 Advanced Compliance componente aggiuntivo.
-   Microsoft 365 E3/A3/A1 abbonamento + il componente aggiuntivo conformità Microsoft 365 E5/A5.
- abbonamento Microsoft 365 E3/A3/A1 + il componente aggiuntivo Gestione dei rischi Insider di Microsoft 365 E5/A5.

> [!NOTE]
> Se sono già configurati [criteri Exchange Online](/exchange/address-books/address-book-policies/address-book-policies) rubrica, è necessario rimuoverli prima di procedere con la procedura seguente.   
> 
> Tutti i passaggi seguenti vengono eseguiti dall'amministratore globale del tenant. 
>   
> Queste istruzioni presuppongono che non siano configurate altre barriere di informazioni.

#### <a name="teams-admin-center"></a>Interfaccia di amministrazione di Teams

1. Accedere [all'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Nel menu della barra di sinistra espandi **Teams**.
3. Selezionare **Impostazioni di Teams**. 
4. Scorrere verso il basso fino a **Cerca per nome**.
5. Attiva l'interruttore e salva la modifica.

Per altre informazioni su questa opzione, vedere [Limitare gli utenti che possono vedere durante la ricerca nella directory in Teams](teams-scoped-directory-search.md).

#### <a name="compliance---auditing"></a>Conformità - Controllo

1. Accedi alla [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com/).
2. Nel riquadro di spostamento sinistro selezionare **Controlla**.
3. Se il controllo è disattivato, verrà visualizzato il banner seguente: 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="Screenshot che mostra il banner di controllo se il controllo non è abilitato":::
  
4. Seleziona **l'attività Avvia registrazione di utenti e amministratori**. 

Per altre informazioni sul controllo, vedere [Configurare il controllo (Standard) in Microsoft 365](/microsoft-365/compliance/audit-standard-setup).

#### <a name="segmenting-data"></a>Segmentazione dei dati

Gli account delle risorse che non devono essere chiamati direttamente devono essere segmentati e facilmente identificabili.  Questa operazione può essere eseguita rendendoli membri di un particolare gruppo o da alcune informazioni univoche nel loro profilo utente, ad esempio: 

-   Società
-   Nome dell'entità utente
-   Posizione
-   Reparto
-   Posizione utilizzo
-   Soprannome della posta elettronica (alias)
-   Nome ufficio consegna fisico (Office)
-   CAP
-   Indirizzo proxy (indirizzo Email)
-   Via e numero civico
-   Indirizzo di destinazione (ExternalEmailAddress)
-   Posta (WindowsEmailAddress)
-   Descrizione

Nei passaggi di esempio seguenti verrà usato il `Department` campo. 

Per altre informazioni sulla segmentazione degli utenti, vedere  [Identificare i segmenti](/microsoft-365/compliance/information-barriers-policies).

#### <a name="microsoft-admin-center"></a>Interfaccia di amministrazione Microsoft

1. Accedere al [Centro Amministrazione Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Nel riquadro di spostamento sinistro selezionare **Utenti attivi**.
3. Selezionare il primo account di risorsa a cui bloccare le chiamate dirette.
4. Selezionare **Gestisci le informazioni di contatto** nel riquadro destro.
5. Sostituire il contenuto del `Department` campo con una parola univoca o un acronimo non usato come nome di reparto. Ad esempio, `DNC`.
6. Salvare le modifiche.
7. Ripetere l'operazione per ogni account di risorsa a cui deve essere impedito di ricevere chiamate dirette.

#### <a name="compliance---information-barriers"></a>Conformità - Barriere informative

1. Accedi alla [Portale di conformità di Microsoft Purview](https://compliance.microsoft.com/).
2. Nel riquadro di spostamento sinistro seleziona **Segmenti di barriere** >  di informazioni.
3. Selezionare **Nuovo segmento**.
4. Immetti un nome per il segmento e seleziona **Avanti**. Ad esempio, `Uncallable Resource Accounts`.
5. Selezionare **+ Aggiungi** e quindi **Reparto**.
6. Immettere la parola univoca o l'acronimo usato nel passaggio 5 dell'interfaccia di amministrazione Microsoft. Ad esempio, `DNC`.
7. Selezionare **Avanti** e quindi **Invia**.
8. Selezionare **Nuovo segmento**.
9. Immetti un nome per il segmento e seleziona **Avanti**. Ad esempio, `Callable Users`.
10. Selezionare **+ Aggiungi** e quindi **Reparto**.
11. Selezionare l'elenco a discesa **Uguale** e scegliere **Diverso da**.
12. Immettere la parola univoca o l'acronimo usato nel passaggio 5 dell'interfaccia di amministrazione Microsoft. Ad esempio, `DNC`.
13. Selezionare **Avanti** e quindi **Invia**. 
14. Nel riquadro di spostamento sinistro selezionare **Criteri barriere** >  informazioni **.**
15. Selezionare **Crea criterio**.
16. Immettere un nome per il criterio e selezionare **Avanti**. Ad esempio, `Uncallable Resource Accounts`.
17. Seleziona **+ Scegli segmento**, aggiungi il segmento creato nel passaggio 9 precedente e seleziona **Avanti**. Ad esempio, `Callable Users`.
18. Selezionare **Bloccato** nell'elenco a discesa **Comunicazione e collaborazione** .
19. Seleziona **+ Scegli segmento**, aggiungi il segmento creato nel passaggio 4 precedente e seleziona **Avanti**. Ad esempio, `Uncallable Resource Accounts`.
20. Impostare il criterio **su Attivato**, selezionare **Avanti** e quindi **Invia**.
21. Selezionare **Crea criterio**.
22. Immettere un nome per il criterio e selezionare **Avanti**. Ad esempio, `Callable Users`.
23. Seleziona **+ Scegli segmento**, aggiungi il segmento creato nel passaggio 4 e seleziona **Avanti**.
24. Selezionare **Bloccato** nell'elenco a discesa **Comunicazione e collaborazione** . 
25. Seleziona **+ Scegli segmento**, aggiungi il segmento creato nel passaggio 9 precedente e seleziona **Avanti**.
26. Impostare il criterio **su Attivato**, selezionare **Avanti** e quindi **Invia**.
27. Nel riquadro di spostamento sinistro selezionare Applicazione **criteri** **barriere** >  informazioni.
28. Selezionare **Applica tutti i criteri**.

> [!NOTE]
> L'applicazione del criterio può richiedere 30 minuti o più.  
> 
> Dopo aver completato lo stato, accedere al client di Teams e cercare gli account delle risorse bloccati. Potrebbe essere necessario cancellare la cache di Teams.  
> 
> Se un utente di Teams ha salvato l'account della risorsa come contatto, non sarà più in grado di chiamarlo.
