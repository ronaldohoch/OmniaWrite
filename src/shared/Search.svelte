<script>
  import { _ } from "svelte-i18n";
  import {
    Input,
    ButtonGroup,
    Button
  } from "../components/Forms";

  import Modal from "./Modal.svelte";

  import { ui } from "../stores";

  let loading = false;
  let searchText="";
</script>

<Modal bind:show={$ui.search.show}>
  <h2 slot="header">{$_('search.title')}</h2>
  <p>{$_('search.sub')}</p>
  <hr />
  <form>
    <Input
      label={$_('search.searchLabel')}
      bind:value={searchText}
      required={true}
      placeholder="" />
    <ButtonGroup>
        <Button {loading}>
            {$_('feedback.action')}
        </Button>
    </ButtonGroup>
  </form>
</Modal>
