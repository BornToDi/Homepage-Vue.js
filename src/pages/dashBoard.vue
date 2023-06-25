<template>
  <q-page padding>
    <!-- content -->
    <div class="">
    <q-layout
      view="hHh Lpr lff"
      container
      style="height: 100vh"
      class="shadow-2 rounded-borders"
    >
      <!--start drawer-->

      <!--finish drawer-->

      <!--page container-->
      <q-page-container>
        <q-page padding>
          <div class="row">
            <div class="col-3 q-px-sm">
              <q-card class="row bg-primary">
                <div class="col-3 q-pa-md">
                  <q-icon
                    class="bg-white rounded-borders"
                    name="print"
                  ></q-icon>
                </div>
                <div class="col-9 q-py-xs text-white">
                  <div>0</div>
                  <div>Total Income</div>
                </div>
              </q-card>
            </div>

            <div class="col-3 q-px-sm">
              <q-card class="row bg-secondary">
                <div class="col-3 q-pa-md">
                  <q-icon
                    class="bg-white rounded-borders"
                    name="print"
                  ></q-icon>
                </div>
                <div class="col-9 q-py-xs text-white">
                  <div>0</div>
                  <div>Total Expenses</div>
                </div>
              </q-card>
            </div>

            <div class="col-3 q-px-sm">
              <q-card class="row bg-warning">
                <div class="col-3 q-pa-md">
                  <q-icon
                    class="bg-white rounded-borders"
                    name="print"
                  ></q-icon>
                </div>
                <div class="col-9 q-py-xs text-white">
                  <div>0</div>
                  <div>Visa Expired Usres</div>
                </div>
              </q-card>
            </div>

            <div class="col-3 q-px-sm">
              <q-card class="row bg-deep-orange">
                <div class="col-3 q-pa-md">
                  <q-icon
                    class="bg-white rounded-borders"
                    name="print"
                  ></q-icon>
                </div>
                <div class="col-9 q-py-xs text-white">
                  <div>0</div>
                  <div>Passport Expired Users</div>
                </div>
              </q-card>
            </div>
          </div>

          <!---->
          <div
            class="row q-py-md q-px-md rounded-borders justify-around"
            style="height: 270px"
          >
            <div class="rounded-borders col-6 shadow-2 q-pr-sm">
              <div class="q-pa-md example-column-row-width">
                <div class="column" style="height: 220px">
                  <div class="col text-weight-bold">Overall Incomes</div>

                  <div class="col-8">
                    <div class="flex flex-center">
                      <q-knob
                        disable
                        v-model="value"
                        show-value
                        size="90px"
                        :thickness="0.22"
                        color="primary"
                        track-color="grey-3"
                        class="text-primary q-ma-md"
                      />
                    </div>
                  </div>

                  <div class="col text-uppercase" style="text-align: center">
                    <span
                      class="bg-yellow-10 text-subtitle2 q-ma-xs rounded-borders text-gray-10"
                      >mail check</span
                    >
                    <span
                      class="bg-info text-subtitle2 q-ma-xs rounded-borders text-gray-10"
                      >visa renewal</span
                    >
                  </div>
                </div>
              </div>
            </div>

            <div class="col-6 shadow-2 q-pr-sm">
              <div class="q-pa-md example-column-row-width">
                <div class="column" style="height: 220px">
                  <div class="col text-weight-bold">Overall Expenses</div>

                  <div class="col-8">
                    <div class="q-pa-md flex flex-center">
                      <q-knob
                        disable
                        v-model="value"
                        show-value
                        size="90px"
                        :thickness="0.22"
                        color="primary"
                        track-color="grey-3"
                        class="text-primary q-ma-md"
                      />
                    </div>
                  </div>

                  <div class="col"></div>
                </div>
              </div>
            </div>
          </div>

          <div class="row q-pt-md q-pl-md">
            <div class="col-6">Overview</div>
            <div class="col-6 position-right">
              <div class="row">
                <div class="col-9"></div>
                <div class="col-3 flex" style="font-size: large">
                  <div class="q-px-xs"><q-icon name="today" /></div>
                  <div class="q-px-xs"><q-icon name="print" /></div>
                  <div class="q-px-xs"><q-icon name="font_download" /></div>
                </div>
              </div>
            </div>
          </div>
          <!---->
          <div class="row">
            <!--first table-->
            <div class="col-6">
              <div class="q-pa-md">
                <q-table
                  flat
                  bordered
                  title="Incomes"
                  :rows="rows"
                  :columns="columns"
                  row-key="name"
                  hide-header
                  hide-bottom
                />
              </div>
            </div>
            <!--finish-->
            <div class="col-6">
              <div class="col-6">
                <div class="q-pa-md">
                  <q-table
                    flat
                    bordered
                    title="Expenses"
                    :rows="rowsS"
                    :columns="columnsS"
                    row-key="name"
                    hide-header
                    hide-bottom
                  />
                </div>
              </div>
            </div>
          </div>
        </q-page>
      </q-page-container>
      <!--finish page container-->
    </q-layout>
  </div>
  </q-page>
</template>

<script>

</script>
