---
title: Configurare il controller dei confini della sessione - Più tenant
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni su come configurare un controller dei confini della sessione (SBC) per la gestione di più tenant per partner Microsoft e/o gestori PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343e2d1aedefd34de452df8da6ce9a5ad1a726ba
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923848"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurare un Session Border Controller per più tenant

L'instradamento diretto supporta la configurazione di un controller dei confini della sessione (SBC) per l'utilizzo di più tenant.

> [!NOTE]
> Questo scenario è progettato per i partner Microsoft e/o i gestori PSTN, indicati come gestori più avanti in questo documento. Un gestore vende servizi di telefonia consegnati a Microsoft Teams ai propri clienti. 

Un corriere:
- Distribuisce e gestisce un SBC nel proprio data center (i clienti non devono implementare un SBC e ricevono servizi di telefonia dal gestore nel client teams).
- Collega l'SBC a più tenant.
- Fornisce servizi PSTN ai clienti.
- Gestisce la qualità delle chiamate end-to-end.
- Addebiti separati per i servizi PSTN.

Microsoft non gestisce i gestori. Microsoft offre un sistema PBX (Sistema telefonico Microsoft) e un client Teams. Microsoft certifica anche i telefoni e certifica i pc che possono essere utilizzati con il Sistema telefonico Microsoft. Prima di scegliere un gestore, assicurati che la tua scelta abbia un SBC certificato e possa gestire la qualità vocale end-to-end.

Di seguito sono descritti i passaggi di implementazione tecnica per configurare lo scenario.

**Solo vettore:**
1. Distribuire il database SBC e configurarlo per lo scenario di hosting in base alle istruzioni dei [fornitori certificati di SBC.](#deploy-and-configure-the-sbc)
2. Registra un nome di dominio di base nel tenant del gestore telefonico e richiedi un certificato con caratteri jolly.
3. Registrare un sottodominio per ogni cliente, che fa parte del dominio di base.

**Vettore con un amministratore globale del cliente:**
1. Aggiungere il nome del sottodominio al tenant del cliente.
2. Attivare il nome del sottodominio.
3. Configurare il trunk dal vettore al tenant del cliente ed eseguire il provisioning degli utenti.

*Assicurarsi di conoscere le nozioni di base sul DNS e su come viene gestito il nome di dominio in Microsoft 365 o Office 365. Vedere [Ottenere assistenza per i domini di Microsoft 365 o Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) prima di procedere ulteriormente.*

## <a name="deploy-and-configure-the-sbc"></a>Distribuire e configurare il servizio SBC

Per la procedura dettagliata su come distribuire e configurare i provider di servizi condivisi per uno scenario di hosting SBC, vedere la documentazione del fornitore del servizio SBC.

- **AudioCodes: Note** [sulla configurazione](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)del routing diretto, configurazione dello scenario di hosting SBC descritto in "Connessione di AudioCodes SBC a Microsoft Teams Direct Routing Hosting Model Configuration Note". 
- **Oracle:** [Note sulla configurazione del routing](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)diretto, la configurazione dello scenario di hosting SBC è descritta nella sezione "Microsoft". 
- **Comunicazioni sulla barra multifunzione:**  Vedere la guida alla configurazione di [Ribbon Communications SBC Core Microsoft Teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) per la documentazione su come configurare gli SBC serie di ribbon e su questa pagina - Procedura consigliata per la configurazione dei gestori di telefonia mobile per Microsoft Teams Direct Routing [SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode):**  Registrarsi nella pagina [TE-Systems Community](https://community.te-systems.de/) per ottenere la documentazione ed esempi su come configurare anynode SBC per più tenant.
- **Metapass:**  Per la documentazione su come abilitare Perimeta SBC per più tenant, registrarsi nella pagina della community [di Metapass.](https://manuals.metaswitch.com/MAN39555)

> [!NOTE]
> Prestare attenzione a come configurare l'intestazione "Contatto". L'intestazione Contatto viene usata per trovare il tenant del cliente nel messaggio di invito in arrivo. 

## <a name="register-a-base-domain-and-subdomains"></a>Registrare un dominio di base e sottodomini

Per lo scenario di hosting, è necessario creare:
- Un nome di dominio di base di proprietà del gestore.
- Un sottodominio che fa parte del nome di dominio di base in ogni tenant dei clienti.

Nell'esempio seguente:
- Adatum è un gestore telefonico che serve diversi clienti con servizi di telefonia e Internet.
- Woodgrove Bank, Contoso e Adventure Works sono tre clienti che hanno domini Microsoft 365 o Office 365 ma ricevono i servizi di telefonia da Adatum.

I sottodomini **DEVONO** corrispondere al nome FQDN del trunk che verrà configurato per il cliente e all'FQDN nell'intestazione Contatto quando si invia l'invito a Microsoft 365 o Office 365. 

Quando una chiamata arriva all'interfaccia di routing diretto di Microsoft 365 o Office 365, l'interfaccia usa l'intestazione Contatto per trovare il tenant in cui l'utente deve essere cercato. L'instradamento diretto non usa la ricerca dei numeri di telefono nell'invito, perché alcuni clienti potrebbero avere numeri non DID che possono sovrapporsi in diversi tenant. Di conseguenza, è necessario il nome FQDN nell'intestazione contatto per identificare il tenant esatto in cui cercare l'utente in base al numero di telefono.

*Per altre  [informazioni sulla](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) creazione di nomi di dominio nelle organizzazioni di Microsoft 365 o Office 365, vedere Ottenere assistenza per i domini di Office 365.*

Il diagramma seguente riepiloga i requisiti per il dominio di base, i sottodomini e l'intestazione contatto.

![Diagramma che mostra i requisiti per i domini e l'intestazione contatto](media/direct-routing-1-sbc-requirements.png)

Il servizio SBC richiede un certificato per autenticare le connessioni. Per lo scenario di hosting SBC, il gestore deve richiedere un certificato con CN e/o SAN *\* .base_domain(ad esempio, \* customers.adatum.biz).* Questo certificato può essere usato per autenticare le connessioni a più tenant serviti da un singolo SBC.


La tabella seguente è un esempio di una configurazione.


|Nuovo nome di dominio |Tipo|Registrata  |Certificate CN/SAN per SBC  |Dominio predefinito del tenant nell'esempio  |Nome FQDN che SBC deve presentare nell'intestazione del contatto quando si inviano chiamate agli utenti|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Nel tenant del corriere  |    \*customers.adatum.biz  |   adatum.biz      |N/D, si tratta di un tenant di servizi, nessun utente |
|sbc1.customers.adatum.biz|    Sottodominio  |    In un tenant del cliente  |    \*customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sottodominio | In un tenant del cliente   |   \*customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sottodominio | In un tenant del cliente |   \*customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Per configurare la base e i sottodomini, seguire la procedura descritta di seguito. Nell'esempio configureremo un nome di dominio di base (customers.adatum.biz) e un sottodominio per un cliente (sbc1.customers.adatum.biz tenant di Woodgrove Bank).

> [!NOTE]
> Usa sbcX.customers.adatum.biz per abilitare la voce nel tenant del gestore. sbcX può essere qualsiasi nome host alfanumerico univoco e valido.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Registra un nome di dominio di base nel tenant del gestore telefonico

**Queste azioni vengono eseguite nel tenant del gestore.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Assicurati di avere diritti appropriati nel tenant del gestore

È possibile aggiungere nuovi domini solo se è stato eseguito l'accesso all'interfaccia di amministrazione di Microsoft 365 come amministratore globale. 

Per convalidare il ruolo, accedere all'interfaccia di amministrazione di Microsoft 365, passare a Utenti attivi e quindi verificare di avere un ruolo di amministratore https://portal.office.com)   >  globale. 

Per altre informazioni sui ruoli di amministratore e su come assegnare un ruolo in Microsoft 365 o Office 365, vedere [Informazioni sui ruoli di amministratore.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Aggiungere un dominio di base al tenant e verificarlo

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Configurazione**  >  **domini**  >  **aggiungi dominio.**
2. Nella casella **Immettere un dominio di cui si** è proprietari digitare il nome di dominio completo del dominio di base. Nell'esempio seguente il dominio di base è *customers.adatum.biz.*

    ![Screenshot che mostra la pagina Aggiungi un dominio](media/direct-routing-2-sbc-add-domain.png)

3. Fare clic su **Avanti**.
4. Nell'esempio, il tenant ha già adatum.biz come nome di dominio verificato. La procedura guidata non richiederà l'ulteriore verifica perché customers.adatum.biz è un sottodominio per il nome già registrato. Tuttavia, se si aggiunge un FQDN non verificato in precedenza, è necessario eseguire il processo di verifica. Il processo di verifica è [descritto di seguito.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![Screenshot che mostra la conferma di un nome di dominio verificato](media/direct-routing-3-sbc-verify-domain.png)

5. Fare **clic** su Avanti, quindi nella pagina **Aggiorna impostazioni DNS** selezionare Aggiungo i record DNS **manualmente** e faccio clic su **Avanti.**
6. Nella pagina successiva deselezionare tutti i valori, a meno che non si desideri utilizzare il nome di dominio per Exchange, SharePoint o Teams/Skype for Business, fare clic su Avanti e quindi su **Fine.** Verificare che il nuovo dominio sia nello stato Configurazione completata.

    ![Screenshot che mostra i domini con lo stato dell'installazione completato](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Attivare il nome di dominio

Dopo aver registrato un nome di dominio, è necessario attivarlo aggiungendo almeno un utente con licenza E1, E3 o E5 e assegnando un indirizzo SIP con la parte FQDN dell'indirizzo SIP corrispondente al dominio di base creato. La licenza può essere revocata dopo l'attivazione del dominio (possono essere richieste fino a 24 ore).

> [!NOTE]
> Il tenant del gestore telefonico deve mantenere almeno una licenza E1/E3/E5/M365 Business assegnata al tenant per evitare la rimozione della configurazione di Skype for Business. 

*Per altre informazioni sull'aggiunta di utenti nelle organizzazioni microsoft 365 o Office 365, vedere Ottenere assistenza per i domini di [Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) o Office 365.*

Ad esempio: test@customers.adatum.biz

![Screenshot della pagina di attivazione del dominio di base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Registrare un nome di sottodominio in un tenant del cliente

Sarà necessario creare un nome di sottodominio univoco per ogni cliente. In questo esempio verrà creato un sbc1.customers.adatum.biz di sottodominio in un tenant con il nome di dominio predefinito woodgrovebank.us.

**Tutte le azioni seguenti sono nel tenant del cliente.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Assicurarsi di avere diritti appropriati nel tenant del cliente

È possibile aggiungere nuovi domini solo se è stato eseguito l'accesso all'interfaccia di amministrazione di Microsoft 365 come amministratore globale. 

Per convalidare il ruolo, accedere all'interfaccia di amministrazione di Microsoft 365, passare a Utenti attivi e quindi verificare di avere un ruolo di amministratore https://portal.office.com)   >  globale. 

Per altre informazioni sui ruoli di amministratore e su come assegnare un ruolo in Microsoft 365 o Office 365, vedere [Informazioni sui ruoli di amministratore.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Aggiungere un sottodominio al tenant del cliente e verificarlo
1. Nell'interfaccia di amministrazione di Microsoft 365 passare a **Configurazione**  >  **domini**  >  **aggiungi dominio.**
2. Nella casella **Immettere un dominio di cui** si è proprietari digitare il nome di dominio completo del sottodominio per il tenant. Nell'esempio seguente il sottodominio è sbc1.customers.adatum.biz.

    ![Screenshot della pagina Aggiungi un dominio](media/direct-routing-5-sbc-add-customer-domain.png)

3. Fare clic su **Avanti**.
4. L'FQDN non è mai stato registrato nel tenant. Nel passaggio successivo sarà necessario verificare il dominio. Selezionare **Aggiungi un record TXT.** 

    ![Screenshot della pagina Verifica dominio](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Fare **clic su** Avanti e prendere nota del valore TXT generato per verificare il nome di dominio.

    ![Screenshot dei record di testo nella pagina Verifica dominio](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Creare il record TXT con il valore del passaggio precedente nel provider di hosting DNS del gestore.

    ![Screenshot che mostra la creazione del record TXT](media/direct-routing-8-sbc-txt-record.png)

    Per altre informazioni, vedere Creare [record DNS presso un provider di hosting DNS.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. Tornare all'interfaccia di amministrazione di Microsoft 365 del cliente e fare clic su **Verifica.** 
8. Nella pagina successiva selezionare Aggiungo i record **DNS** manualmente e faccio clic su **Avanti.**

    ![Screenshot delle opzioni nella pagina Aggiorna impostazioni DNS](media/direct-routing-9-sbc-update-dns.png)

9. Nella pagina **Scegli i servizi online** deselezionare tutte le opzioni e fare clic su **Avanti.**

    ![Screenshot della pagina Scegli i servizi online](media/direct-routing-10-sbc-choose-services.png)

10. Fare **clic su** Fine nella pagina Aggiorna impostazioni **DNS.**

    ![Screenshot della pagina Aggiorna impostazioni DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Verificare che lo stato sia **Installazione completata.** 
    
    ![Screenshot della pagina che mostra lo stato dell'installazione completata](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> L'URL di base e il sottodominio per il singolo client devono essere nello stesso tenant per consentire l'aggiunta di un trunk _di percorso diretto._

### <a name="activate-the-subdomain-name"></a>Attivare il nome del sottodominio

Dopo aver registrato un nome di dominio, è necessario attivarlo aggiungendo almeno un utente e assegnando un indirizzo SIP con la parte FQDN dell'indirizzo SIP corrispondente al sottodominio creato nel tenant del cliente. La licenza può essere revocata dall'utente dopo l'attivazione del sottodominio (possono essere richieste fino a 24 ore).

*Per altre informazioni sull'aggiunta di utenti nelle organizzazioni microsoft 365 o Office 365, vedere Ottenere assistenza per i domini di [Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) o Office 365.*

Ad esempio: test@sbc1.customers.adatum.biz

![Screenshot della pagina Di attivazione del sottodominio](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Creare un trunk ed eseguire il provisioning degli utenti

Con il rilascio iniziale del routing diretto, Microsoft ha richiesto l'aggiunta di un trunk a ogni tenant notificato (tenant del cliente) usando New-CSOnlinePSTNGateway.

Tuttavia, questa scelta non è risultata ottimale per due motivi:
 
- **Gestione dei costi.** L'offload o l'escolo di un SBC, ad esempio, modifica alcuni parametri, come l'abilitazione o la disabilitazione del bypass multimediale. La modifica della porta richiede la modifica dei parametri in più tenant (eseguendo Set-CSOnlinePSTNGateway), ma in realtà si tratta dello stesso SBC. 

-  **Elaborazione sovraccarico.** Raccolta e monitoraggio dei dati di integrità del trunk: le opzioni SIP raccolte da più trunk logici, in realtà lo stesso SBC e lo stesso trunk fisico, rallentano l'elaborazione dei dati di routing.
 
In base a questo feedback, Microsoft sta portando avanti una nuova logica per il provisioning dei trunk per i tenant del cliente.

Sono state introdotte due nuove entità:
-    Un trunk di vettore registrato nel tenant del gestore telefonico con il comando New-CSOnlinePSTNGateway, ad esempio New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    Un trunk derivato, che non richiede la registrazione. Si tratta semplicemente di un nome host desiderato aggiunto dal trunk del corriere. Ricava tutti i parametri di configurazione dal trunk del gestore. Non è necessario creare il trunk derivato in PowerShell e l'associazione con il trunk del vettore si basa sul nome FQDN (vedere i dettagli di seguito).

**Logica di provisioning e esempio**

-    I gestori di telefonia mobile devono configurare e gestire un singolo trunk (trunk del vettore nel dominio del vettore), usando il comando Set-CSOnlinePSTNGateway spedizione. Nell'esempio precedente è adatum.biz;
-    Nel tenant del cliente, il gestore deve aggiungere l'FQDN del trunk derivato ai criteri di routing vocale degli utenti. Non è necessario eseguire il New-CSOnlinePSTNGateway per un trunk.
-    Il trunk derivato, come suggerisce il nome, eredita o ricava tutti i parametri di configurazione dal trunk del vettore. Esempi:
-    Customers.adatum.biz, ovvero il trunk del vettore che deve essere creato nel tenant del corriere.
-    Sbc1.customers.adatum.biz: il trunk derivato in un tenant del cliente che non deve essere creato in PowerShell.  È possibile aggiungere semplicemente il nome del trunk derivato nel tenant del cliente nel criterio di routing vocale online senza crearlo.
-   L'operatore dovrà configurare il record DNS che risolve l'FQDN trunk derivato all'indirizzo IP SBC del vettore.

-    Qualsiasi modifica apportata al trunk di un vettore (tenant del vettore) viene applicata automaticamente ai trunk derivati. Ad esempio, i gestori possono modificare una porta SIP nel trunk del vettore e questa modifica si applica a tutti i trunk derivati. La nuova logica per configurare i trunk semplifica la gestione perché non è necessario accedere a ogni tenant e modificare il parametro in ogni trunk.
-    Le opzioni vengono inviate solo all'FQDN trunk del vettore. Lo stato di integrità del trunk del vettore viene applicato a tutti i trunk derivati e viene usato per le decisioni di routing. Altre informazioni sulle [opzioni per l'instradamento diretto.](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot)
-    Il vettore può drenare il trunk del corriere e anche tutti i trunk derivati verranno scaricati. 
 

**Migrazione dal modello precedente al trunk del gestore telefonico**
 
Per la migrazione dall'implementazione corrente del modello ospitato dal vettore al nuovo modello, i gestori dovranno riconfigurare i trunk per i tenant dei clienti. Rimuovi i trunk dai tenant dei clienti usando Remove-CSOnlinePSTNGateway (lasciando il trunk nel tenant del gestore)-

Consigliamo vivamente di eseguire la migrazione alla nuova soluzione il più presto possibile, perché il monitoraggio e il provisioning verranno migliorati usando il vettore e il modello di trunk derivato.
 

Vedere le istruzioni del fornitore [di SBC](#deploy-and-configure-the-sbc) per configurare l'invio del nome FQDN dei sottodomini nell'intestazione Contatto.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Considerazioni per la configurazione del failover muti-tenant 

Per configurare il failover per un ambiente multi-tenant, è necessario eseguire le operazioni seguenti:

- Per ogni tenant, aggiungere gli FQDN per due diversi SBC.  Ad esempio:

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Nei criteri di routing vocale online degli utenti specificare entrambi gli SBC.  Se un solo SBC ha esito negativo, il criterio di routing instraderà le chiamate al secondo SBC.


## <a name="see-also"></a>Vedere anche

[Pianificare Instradamento diretto](direct-routing-plan.md)

[Configurare Instradamento diretto](direct-routing-configure.md)
