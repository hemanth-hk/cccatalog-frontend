<template>
  <div v-if="sourceURL" class="legal-disclaimer">
    <h4 class="b-header">Verify at the source</h4>
    <div class="margin-top-normal">
      <ul>
        <li class="caption margin-bottom-small">
          CC Search aggregates data from publicly available repositories of open content.
        </li>
        <li class="caption margin-bottom-small">
          CC does not host the content and does not verify that the content is properly
          CC-licensed or that the attribution information is accurate or complete.
        </li>
        <li class="caption margin-bottom-small">
          Please follow the link to the source of the content to independently verify before reuse.
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Tooltip from '@/components/Tooltip';
import getProviderLogo from '@/utils/getProviderLogo';

export default {
  name: 'legal-disclaimer',
  props: ['source', 'sourceProviderCode', 'sourceURL'],
  components: {
    Tooltip,
  },
  methods: {
    getProviderLogo(providerName) {
      return getProviderLogo(providerName);
    },
  },
};
</script>

<style lang="scss" scoped>
  li:before{
    content: "\2022";
    color: #CCC;
    font-weight: bold;
    display: inline-block;
    margin-right: .5rem;
    font-size: 1rem;
  }
</style>
