<template>
  <div class="q-pa-md" style="max-width: 300px">
    <q-dialog v-model="alert">
      <q-card>
        <q-card-section>
          <div class="text-h6">Nowy</div>
        </q-card-section>

        <q-card-section>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate voluptas eveniet porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam exercitationem aut, natus minima, porro labore.</q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="OK" color="primary" v-close-popup/>
        </q-card-actions>
      </q-card>
    </q-dialog>

    <div class="q-gutter-md">
      <q-select
          standout="bg-deep-orange-3 text-white"
          stack-label
          filled
          label="Standard"
          v-model="model"
          :options="options"
          color="teal"
          options-selected-class="text-deep-orange"
      >
        <template v-slot:prepend>
          <q-icon name="mail"/>
        </template>

        <template v-slot:option="scope" class="text-white">
          <q-item v-bind="scope.itemProps" v-on="scope.itemEvents">
            <q-item-section avatar>
              <q-icon :name="scope.opt.icon"/>
            </q-item-section>
            <q-item-section>
              <q-item-label v-html="scope.opt.label"/>
              <q-item-label caption>{{ scope.opt.description }}</q-item-label>
            </q-item-section>
            <q-item-section side>
              <q-btn flat round color="primary" icon="clear"/>
            </q-item-section>
          </q-item>
        </template>

        <template v-slot:append>
          <q-icon v-if="model !== ''" name="add" @click.stop="alert = true" class="cursor-pointer"/>
        </template>
      </q-select>
    </div>
  </div>
</template>

<style>
</style>

<script>
    export default {
        name: 'PageIndex',
        data() {
            return {
                model: null,
                alert: false,
                options: [
                    {
                        label: 'Paczka 32kg',
                        value: '1',
                        description: '12 x 12 x 120cm',
                        icon: 'border_all'
                    },
                    {
                        label: 'Koperta',
                        value: '2',
                        description: '12 x 12 x 12cm',
                        icon: 'mail'
                    },
                    {
                        label: 'Paleta 111kg',
                        value: '3',
                        description: '60 x 80 x 120cm',
                        icon: 'border_bottom'
                    },
                    {
                        label: 'Paleta 79kg',
                        value: '4',
                        description: '60 x 80 x 120cm',
                        icon: 'border_bottom'
                    },
                    {
                        label: 'Paleta 180kg',
                        value: '5',
                        description: '60 x 80 x 120cm',
                        icon: 'border_bottom'
                    }
                ]
            }
        }
    }
</script>
