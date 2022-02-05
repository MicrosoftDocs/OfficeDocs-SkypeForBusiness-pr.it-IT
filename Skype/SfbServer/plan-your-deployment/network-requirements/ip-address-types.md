---
title: Configurare i tipi di indirizzi IP in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Riepilogo: esaminare le considerazioni sul tipo di indirizzo IP riportate di seguito prima di implementare Skype for Business Server.'
---

# <a name="configure-ip-address-types-in-skype-for-business"></a>Configurare i tipi di indirizzi IP in Skype for Business

**Riepilogo:** Leggere le considerazioni sul tipo di indirizzo IP riportate di seguito prima di implementare Skype for Business Server.

I tipi di indirizzi IP vengono distribuiti utilizzando le impostazioni della topologia configurate in Generatore di topologie. In questa sezione viene descritto come distribuire tipi di indirizzi IP in Front End Server, Mediation Server e server perimetrali.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>Distribuire tipi di indirizzi IP in un Front End Server

Utilizzando Generatore di topologie, eseguire i passaggi della procedura seguente per distribuire i tipi di indirizzi IP in un Front End Server.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>Per distribuire i tipi di indirizzi IP in un Front End Server

1. In **Pool Enterprise Edition Front End** fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi scegliere **Modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.

2. Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**.

   **Finestra di dialogo Modifica proprietà per il pool Front End Server**

   - **Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.

     > [!NOTE]
     > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

   - **Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un determinato indirizzo da utilizzare nel nuovo server. Se si seleziona questa opzione, sarà necessario immettere un valore per **Indirizzo IP primario**.

   - **Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, tranne quelle su rete PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.

   - **Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel Front End Server. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.

> [!NOTE]
> L'installazione di schede di interfaccia di rete aggiuntive (NIC) per supportare la configurazione degli indirizzi IP PSTN (o per qualsiasi altro motivo) nei Front End Server non è supportata. Per ulteriori informazioni sulle configurazioni NIC supportate per Skype for Business Server, vedere [Server hardware platforms for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>Distribuire tipi di indirizzi IP in un Mediation Server

Utilizzando Generatore di topologie, eseguire i passaggi della procedura seguente per distribuire i tipi di indirizzi IP in un Mediation Server.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>Per distribuire i tipi di indirizzi IP in un Mediation Server

- In Generatore di topologie, in **Pool Mediation Server**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi **scegliere Modifica proprietà**. In alternativa, selezionare il server e quindi scegliere **Modifica proprietà** dal menu **Azione**.

- Nella finestra di dialogo **Modifica proprietà** selezionare il tipo di indirizzo IP che si desidera configurare. Per una configurazione con dual stack, selezionare **Abilita IPv4** e **Abilita IPv6**, come illustrato nella figura seguente.

   **Finestra di dialogo Modifica proprietà per il pool Mediation Server**

  - **Usa tutti gli indirizzi IP configurati**. Selezionare questa opzione se si desidera consentire l'utilizzo di qualsiasi indirizzo IP definito nel computer.

    > [!NOTE]
    > Questa è l'opzione consigliata per le configurazioni IP versione 6 (IPv6).

  - **Limita utilizzo servizio a indirizzi IP selezionati**. Selezionare questa opzione per specificare un indirizzo specifico da utilizzare nel nuovo server. Se si seleziona questa opzione è necessario immettere un valore per Indirizzo IP primario.

  - **Indirizzo IP primario**. Immettere un indirizzo IP che verrà utilizzato dal server per tutte le comunicazioni, ad eccezione di PSTN (Public Switched Telephone Network). L'indirizzo IP immesso deve corrispondere al formato del tipo di indirizzo selezionato.

  - **Indirizzo IP PSTN**. Definire un indirizzo IP PSTN quando un Mediation Server è collocato nel Front End Server. Questo indirizzo deve corrispondere al formato del tipo di indirizzo selezionato.
> [!IMPORTANT]
> Sono supportate solo due schede di rete *su* Mediation Server dedicati. Se il ruolo Mediation Sserver è collocato nel Front End, le schede di rete doppie non sono supportate. 

> [!NOTE]
> - Per ulteriori informazioni sulle configurazioni NIC supportate per Skype for Business Server 2015, vedere [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)
> - Per ulteriori informazioni sulle configurazioni NIC supportate per Skype for Business Server 2019, vedere [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)



## <a name="deploy-ip-address-types-on-an-edge-server"></a>Distribuire tipi di indirizzi IP in un server perimetrale

Utilizzando Generatore di topologie, eseguire la procedura seguente:

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Per distribuire tipi di indirizzo IP su un server perimetrale

1. In Generatore di topologie, in **Pool di server perimetrali**, fare clic con il pulsante destro del mouse sul server all'interno di un pool e quindi **scegliere Modifica proprietà**. (Alternativamente, selezionare il server e fare clic su **Modifica proprietà** dal menu **Azione**.)

2. Nella finestra **Modifica proprietà**, selezionare la configurazione dell'indirizzo IP che si desidera supportare.

3. Per ciascun tipo di indirizzo selezionato, è necessario fornire gli indirizzi interni e esterni appropriati.