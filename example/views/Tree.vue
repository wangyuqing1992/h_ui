<template>
  <div>
    <h-row>
      <h-col span='6'><h2>基本用法</h2><h-tree :data="data1"></h-tree></h-col>
      <h-col span='6'><h2>显示勾选框</h2><h-tree :data="data2" show-checkbox @on-check-change="checkChnage"></h-tree></h-col>
      <h-col span='6'><h2>异步加载</h2><h-tree :data="data3" :load-data="loadData" show-checkbox></h-tree> </h-col>
      <h-col span='6'><h2>默认展开、选中、勾选和禁用</h2><h-tree :data="data4" show-checkbox multiple></h-tree> </h-col>
    </h-row>
    <h-row>
      <h-col span='6'><h2>多选</h2><h-tree :data="data11" multiple></h-tree></h-col>
      <h-col span='6'><h2>父子组件不联动</h2><h-tree :data="data22" show-checkbox checkStrictly @on-check-change="checkChnage"></h-tree></h-col>
      <h-col span='6'><h2>不显示不确定性状态</h2><h-tree :data="data33" show-checkbox showIndeterminate></h-tree> </h-col>
      <h-col span='6'><h2>自定义节的内容</h2> <h-tree :data="data5" :render="renderContent"></h-tree></h-col>
    </h-row>
    <h-row>
      <h-col span="8">
        <h-tree :data="baseData" show-checkbox @on-check-change="handleChange" @on-toggle-expand="showExpand"></h-tree>
      </h-col>
      <h-col span="8">
        <h-tree :data="baseData3" show-checkbox showIndeterminate></h-tree>
      </h-col>
      <h-col span="8">
        <h2>123</h2>
        <h-tree :data="baseData2" @on-select-change="showChange" ></h-tree>
      </h-col>
    </h-row>
    <h-row>
      <h-col span="8">
        <h-tree :data="baseData1" show-checkbox checkStrictly></h-tree>
      </h-col>
      <h-col span="8">
        <h-tree :data="baseData2" show-checkbox ></h-tree>
      </h-col>
      <h-col span="8">
        <h-tree :data="baseData2" @on-select-change="showChange" ></h-tree>
      </h-col>
    </h-row>
  </div>
</template>
<script>
  export default {
    data () {
      return {
        bd: [],
        baseData: [
          {
            title: 'parent',
            id: '1-0',
            expand: true,
            children: [
              {
                title: 'child1',
                id: '1-1',
                expand: true,
                children: [
                  {
                    title: 'child1-1-1',
                    id: '1-1-1'
                  },
                  {
                    title: 'child1-1-2',
                    id: '1-1-2'
                  }
                ]
              },
              {
                title: 'child2',
                id: '1-2',
                children: []
              }
            ]
          }
        ],
        baseData1: [
          {
            title: 'parent',
            id: '1-0',
            expand: true,
            children: [
              {
                title: 'child1',
                id: '1-1',
                expand: true,
                children: [
                  {
                    title: 'child1-1-1',
                    id: '1-1-1'
                  },
                  {
                    title: 'child1-1-2',
                    id: '1-1-2'
                  }
                ]
              },
              {
                title: 'child2',
                id: '1-2',
                children: []
              }
            ]
          }
        ],
        baseData2: [{
            expand: true,
            title: 'parent 1',
            children: [{
              title: 'parent 1-0',
              expand: true,
              disabled: true,
              children: [{
                title: 'leaf',
                disableCheckbox: true
              }, {
                title: 'leaf',
              }]
            }, {
              title: 'parent 1-1',
              expand: true,
              checked: true,
              children: [{
                title: '<span style="color: red">leaf</span>',
              }]
            }]
        }],
        baseData3: [
          {
            title: 'parent',
            id: '1-0',
            expand: true,
            children: [
              {
                title: 'child1',
                id: '1-1',
                expand: true,
                children: [
                  {
                    title: 'child1-1-1',
                    id: '1-1-1'
                  },
                  {
                    title: 'child1-1-2',
                    id: '1-1-2'
                  }
                ]
              },
              {
                title: 'child2',
                id: '1-2',
                children: []
              }
            ]
          }
        ],
        data1: [
          {
            title: 'parent 1',
            expand: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                disabled:true,
                children: [
                    {
                        title: 'leaf 1-1-1'
                    },
                    {
                        title: 'leaf 1-1-2'
                    }
                ]
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                    {
                        title: 'leaf 1-2-1'
                    },
                    {
                        title: 'leaf 1-2-1'
                    }
                ]
              }
            ]
          }
        ],
        data2: [
          {
            title: 'parent 1',
            expand: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                checked: true,
                children: [
                  {
                    title: 'leaf 1-1-1'
                  },
                  {
                    title: 'leaf 1-1-2'
                  }
                ]
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-2-1'
                  },
                  {
                    title: 'leaf 1-2-1'
                  }
                ]
              }
            ]
          }
        ],
        data3: [
          {
            title: 'parent',
            loading: false,
            children: []
          }
        ],
        data11: [
          {
            title: 'parent 1',
            expand: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                children: [
                    {
                        title: 'leaf 1-1-1'
                    },
                    {
                        title: 'leaf 1-1-2'
                    }
                ]
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                    {
                        title: 'leaf 1-2-1'
                    },
                    {
                        title: 'leaf 1-2-1'
                    }
                ]
              }
            ]
          }
        ],
        data22: [
          {
            title: 'parent 1',
            expand: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                checked: true,
                children: [
                  {
                    title: 'leaf 1-1-1'
                  },
                  {
                    title: 'leaf 1-1-2'
                  }
                ]
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-2-1'
                  },
                  {
                    title: 'leaf 1-2-1'
                  }
                ]
              }
            ]
          }
        ],
        data33: [
          {
            title: 'parent 1',
            expand: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-1-1'
                  },
                  {
                    title: 'leaf 1-1-2'
                  }
                ]
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-2-1'
                  },
                  {
                    title: 'leaf 1-2-1'
                  }
                ]
              }
            ]
          }
        ],
        data4: [
          {
            title: 'parent 1',
            expand: true,
            selected: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-1-1',
                    disabled: true
                  },
                  {
                    title: 'leaf 1-1-2',
                    disableCheckbox:true
                  }
                ]
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-2-1',
                    checked: true
                  },
                  {
                    title: 'leaf 1-2-1'
                  }
                ]
              }
            ]
          }
        ],
        data5: [
          {
            title: 'parent 1',
            expand: true,
            render: (h, { root, node, data }) => {
              return h('span', {
                  style: {
                      display: 'inline-block',
                      width: '100%'
                  }
              }, [
                  h('span', [
                    h('h-icon', {
                        props: {
                          name: 'android-folder-open'
                        },
                        style: {
                          marginRight: '8px'
                        }
                    }),
                    h('span', data.title)
                  ]),
                  h('span', {
                    style: {
                        display: 'inline-block',
                        float: 'right',
                        marginRight: '32px'
                    }
                  }, [
                    h('h-button', {
                      props: Object.assign({}, this.buttonProps, {
                          icon: 'plus',
                          type: 'primary'
                      }),
                      style: {
                          width: '52px'
                      },
                      on: {
                          click: () => { this.append(data) }
                      }
                    })
                  ])
              ]);
            },
            children: [
              {
                title: 'child 1-1',
                expand: true,
                children: [
                  {
                      title: 'leaf 1-1-1',
                      expand: true
                  },
                  {
                      title: 'leaf 1-1-2',
                      expand: true
                  }
                ]
              },
              {
                title: 'child 1-2',
                expand: true,
                children: [
                  {
                      title: 'leaf 1-2-1',
                      expand: true
                  },
                  {
                      title: 'leaf 1-2-1',
                      expand: true
                  }
                ]
              }
            ]
          }
        ],
        buttonProps: {
          type: 'ghost',
          size: 'small',
        }
      }
    },
    methods: {
      loadData (item, callback) {
        setTimeout(() => {
          const data = [
            {
              title: 'children',
              loading: false,
              children: []
            },
            {
              title: 'children',
              loading: false,
              children: []
            }
          ];
          callback(data);
        }, 1000);
      },
      renderContent (h, { root, node, data }) {
          return h('span', {
              style: {
                  display: 'inline-block',
                  width: '100%'
              }
          }, [
              h('span', [
                  h('h-icon', {
                      props: {
                        name: 'ios-paper-outline'
                      },
                      style: {
                        marginRight: '8px'
                      }
                  }),
                  h('span', data.title)
              ]),
              h('span', {
                  style: {
                      display: 'inline-block',
                      float: 'right',
                      marginRight: '32px'
                  }
              }, [
                  h('h-button', {
                      props: Object.assign({}, this.buttonProps, {
                          icon: 'plus-round'
                      }),
                      style: {
                          marginRight: '8px'
                      },
                      on: {
                          click: () => { this.append(data) }
                      }
                  }),
                  h('h-button', {
                      props: Object.assign({}, this.buttonProps, {
                          icon: 'minus-round'
                      }),
                      on: {
                          click: () => { this.remove(root, node, data) }
                      }
                  })
              ])
          ]);
      },
      append (data) {
          const children = data.children || [];
          children.push({
              title: 'appended node',
              expand: true
          });
          this.$set(data, 'children', children);
      },
      remove (root, node, data) {
          const parentKey = root.find(el => el === node).parent;
          const parent = root.find(el => el.nodeKey === parentKey).node;
          const index = parent.children.indexOf(data);
          parent.children.splice(index, 1);
      },
      handleSelectChange (data) {
        // console.log(data);
      },
      updateTree (data) {
        data[0].children[0].checked = true;
        data[0].children[0].children[0].checked = true;
        data[0].children[0].children[1].checked = true;
      },
      handleChange () {
        // console.log(1)
      },
      showChange(arr){
        console.log(arr)
      },
      showExpand (payload) {
        console.log(payload)
      },
      checkChnage(data){
        console.log(data);
      }
    },
    mounted () {
      // this.updateTree(this.baseData);
    }
  }
</script>