<template>
  <t-space direction="vertical">
    <t-list :split="true">
      <t-list-item>
        <t-list-item-meta :image="avatarUrl" title="列表主内容" description="列表内容列表内容" />
        <template #action>
          <span>
            <t-button variant="text">操作1</t-button>
            <t-button variant="text">操作2</t-button>
            <t-button variant="text">操作3</t-button>
          </span>
        </template>
      </t-list-item>
      <t-list-item>
        <t-list-item-meta :image="avatarUrl" title="列表主内容" description="列表内容列表内容" />
        <template #action>
          <span>
            <t-button variant="text">操作1</t-button>
            <t-button variant="text">操作2</t-button>
            <t-button variant="text">操作3</t-button>
          </span>
        </template>
      </t-list-item>
    </t-list>

    <t-list :split="true">
      <t-list-item>
        <t-list-item-meta :image="avatarUrl" title="列表主内容" description="列表内容列表内容" />
        <template #action>
          <t-button variant="text" shape="square">
            <edit-icon />
          </t-button>
          <t-button variant="text" shape="square">
            <download-icon />
          </t-button>
        </template>
      </t-list-item>
      <t-list-item>
        <t-list-item-meta :image="avatarUrl" title="列表主内容" description="列表内容列表内容" />
        <template #action>
          <t-button variant="text" shape="square">
            <edit-icon />
          </t-button>
          <t-button variant="text" shape="square">
            <download-icon />
          </t-button>
        </template>
      </t-list-item>
    </t-list>
  </t-space>
</template>

<script setup>
import { EditIcon, DownloadIcon } from 'tdesign-icons-vue-next';

const avatarUrl = 'https://tdesign.gtimg.com/site/avatar.jpg';
</script>
