//示例代码
<template>
  <div id="tree" style="">
    <div class="container">
      <div class="col-md-10 col-md-offset-1">
        <div class="page-header">
          <h3>招行度量指标体系</h3>
        </div>
        <div class="row">
          <div class="col-md-8 col-md-offset-2">
            <form class="form-horizontal row">
              <div class="col-md-4">
                <div class="checkbox">
                  <label>
                    <input type="checkbox" v-model="horizontal" /> 横排
                  </label>
                </div>
              </div>
              <div class="col-md-4">
                <div class="checkbox">
                  <label>
                    <input type="checkbox" v-model="collapsable" /> 竖排
                  </label>
                </div>
              </div>
              <div class="col-md-4">
                <div class="checkbox">
                  <label>
                    <input type="checkbox" v-model="expandAll" @change="expandChange" /> 显示所有项
                  </label>
                </div>
              </div>
              <p>
                <br />
              </p>
              <p>
                <br />
              </p>
              <div class="col-md-6">
                <div class="form-group">
                  <label class="control-label col-md-5">背景色选择:</label>
                  <div class="col-md-7">
                    <select class="form-control" v-model="labelClassName">
                      <option value="bg-blue">bg-blue</option>
                      <option value="bg-white">bg-white</option>
                      <option value="bg-black">bg-black</option>
                      <option value="bg-green">bg-green</option>
                      <option value="bg-orange">bg-orange</option>
                      <option value="bg-yellow">bg-yellow</option>
                    </select>
                  </div>
                </div>
              </div>
            </form>
          </div>
        </div>
        <p>
          <br />
        </p>
        <div class="text-center">
          <vue2-org-tree
                  name="test"
                  :data="data"
                  :horizontal="horizontal"
                  :collapsable="collapsable"
                  :label-class-name="labelClassName"
                  :render-content="renderContent"
                  @on-expand="onExpand"
                  @on-node-click="onNodeClick"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        data: {
          id: 0,
          label: "度量指标体系",
          children: [
            {
              id: 1,
              label: "交付质量",
              children: [
                {
                  id: 11,
                  label: "生产质量",
                  children: [
                    {
                      id: 111,
                      label: "生产事件"
                    }
                  ]
                },
                {
                  id: 12,
                  label: "开发质量",
                  children: [
                    {
                      id: 121,
                      label: "项目开发缺陷密度"
                    }
                  ]
                },
                {
                  id: 13,
                  label: "发布质量",
                  children: [
                    {
                      id: 131,
                      label: "上线失败率"
                    }
                  ]
                },
                {
                  id: 14,
                  label: "过程质量",
                  children: [
                    {
                      id: 141,
                      label: "项目过程符合度"
                    }
                  ]
                }
              ]
            },
            {
              id: 2,
              label: "交付效能",
              children: [
                {
                  id: 21,
                  label: "交付能力",
                  children: [
                    {
                      id: 211,
                      label: "功能点产出"
                    },
                    {
                      id: 212,
                      label: "代码行产出"
                    },
                    {
                      id: 213,
                      label: "上线投产次数"
                    },
                    {
                      id: 214,
                      label: "接收需求数"
                    },
                    {
                      id: 215,
                      label: "立项数"
                    },
                    {
                      id: 216,
                      label: "结项数"
                    },
                    {
                      id: 217,
                      label: "迭代速率"
                    },
                    {
                      id: 218,
                      label: "迭代完成率"
                    }
                  ]
                },
                {
                  id: 22,
                  label: "交付效率",
                  children: [
                    {
                      id: 221,
                      label: "人均产出功能点"
                    },
                    {
                      id: 222,
                      label: "项目生产率"
                    }
                  ]
                }
              ]
            },
            {
              id: 3,
              label: "业务满意度",
              children: [
                {
                  id: 31,
                  label: "业务满意度"
                }
              ]
            },
            {
              id: 4,
              label: "交付价值",
              children: [
                {
                  id: 41,
                  label: "业务价值关键指标"
                }
              ]
            },
            {
              id: 5,
              label: "交付速度",
              children: [
                {
                  id: 51,
                  label: "需求评估速度",
                  children: [
                    {
                      id: 511,
                      label: "需求响应度"
                    }
                  ]
                },
                {
                  id: 52,
                  label: "开发速度",
                  children: [
                    {
                      id: 521,
                      label: "完成度天数"
                    },
                    {
                      id: 522,
                      label: "完成度达标率"
                    },
                    {
                      id: 523,
                      label: "故事平均测试通过周期"
                    }
                  ]
                },
                {
                  id: 53,
                  label: "发布速度",
                  children: [
                    {
                      id: 531,
                      label: "首次交付天数"
                    },
                    {
                      id: 532,
                      label: "首次交付达标率"
                    },
                    {
                      id: 533,
                      label: "故事平均发布周期"
                    }
                  ]
                },
                {
                  id: 54,
                  label: "燃尽图"
                },
                {
                  id: 55,
                  label: "一次测试通过率"
                }
              ]
            },
            {
              id: 6,
              label: "持续交付",
              children: [
                {
                  id: 61,
                  label: "技术债务率",
                  url: "https://world.taobao.com/"
                },
                {
                  id: 62,
                  label: "DEVOPS成熟度",
                  url: " http://www.baidu.com"
                },
                {
                  id: 63,
                  label: "DEVOPS健康度",
                  url: " https://www.google.com/"
                }
              ]
            }
          ]
        },
        horizontal: true,
        collapsable: true,
        expandAll: false,
        labelClassName: "bg-blue"
      };
    },
    methods: {
      renderContent(h, data) {
        return data.label;
      },
      onExpand(e, data) {
        if ("expand" in data) {
          data.expand = !data.expand;
          if (!data.expand && data.children) {
            this.collapse(data.children);
          }
        } else {
          this.$set(data, "expand", true);
        }
      },
      //点击选项执行的方法，可以用于跳转到其他链接，注意一定要写协议头
      onNodeClick(e, data) {
        //console.log(data.label);
        if(data.url==null){
          return false
        }else{
          window.open(data.url)
        }
      },
      collapse(list) {
        var _this = this;
        list.forEach(function(child) {
          if (child.expand) {
            child.expand = false;
          }
          child.children && _this.collapse(child.children);
        });
      },
      expandChange() {
        this.toggleExpand(this.data, this.expandAll);
      },
      toggleExpand(data, val) {
        var _this = this;
        if (Array.isArray(data)) {
          data.forEach(function(item) {
            _this.$set(item, "expand", val);
            if (item.children) {
              _this.toggleExpand(item.children, val);
            }
          });
        } else {
          this.$set(data, "expand", val);
          if (data.children) {
            _this.toggleExpand(data.children, val);
          }
        }
      }
    }
  };
</script>
<style lang="less">
  .org-tree-container {
    display: inline-block;
    padding: 15px;
    background-color: #fff;
  }

  .org-tree {
  // display: inline-block;
    display: table;
    text-align: center;

  &:before, &:after {
     content: '';
     display: table;
   }

  &:after {
     clear: both;
   }
  }

  .org-tree-node,
  .org-tree-node-children {
    position: relative;
    margin: 0;
    padding: 0;
    list-style-type: none;

  &:before, &:after {
               transition: all .35s;
             }
  }
  .org-tree-node-label {
    position: relative;
    display: inline-block;

  .org-tree-node-label-inner {
    padding: 10px 15px;
    text-align: center;
    border-radius: 3px;
    box-shadow: 0 1px 5px rgba(0, 0, 0, .15);
  }
  }
  .org-tree-node-btn {
    position: absolute;
    top: 100%;
    left: 50%;
    width: 20px;
    height: 20px;
    z-index: 10;
    margin-left: -11px;
    margin-top: 9px;
    background-color: #fff;
    border: 1px solid #ccc;
    border-radius: 50%;
    box-shadow: 0 0 2px rgba(0, 0, 0, .15);
    cursor: pointer;
    transition: all .35s ease;

  &:hover {
     background-color: #e7e8e9;
     transform: scale(1.15);
   }

  &:before, &:after {
               content: '';
               position: absolute;
             }

  &:before {
     top: 50%;
     left: 4px;
     right: 4px;
     height: 0;
     border-top: 1px solid #ccc;
   }

  &:after {
     top: 4px;
     left: 50%;
     bottom: 4px;
     width: 0;
     border-left: 1px solid #ccc;
   }

  &.expanded:after {
     border: none;
   }
  }
  .org-tree-node {
    padding-top: 20px;
    display: table-cell;
    vertical-align: top;

  &.is-leaf, &.collapsed {
      padding-left: 10px;
      padding-right: 10px;
  }

  &:before, &:after {
       content: '';
       position: absolute;
       top: 0;
       left: 0;
       width: 50%;
       height: 19px;
  }

  &:after {
     left: 50%;
     border-left: 1px solid #ddd;
   }

  &:not(:first-child):before,
  &:not(:last-child):after {
     border-top: 1px solid #ddd;
   }

  }
  .collapsable .org-tree-node.collapsed {
    padding-bottom: 30px;

  .org-tree-node-label:after {
    content: '';
    position: absolute;
    top: 100%;
    left: 0;
    width: 50%;
    height: 20px;
    border-right: 1px solid #ddd;
  }
  }
  .org-tree > .org-tree-node {
    padding-top: 0;

  &:after {
     border-left: 0;
   }
  }
  .org-tree-node-children {
    padding-top: 20px;
    display: table;

  &:before {
     content: '';
     position: absolute;
     top: 0;
     left: 50%;
     width: 0;
     height: 20px;
     border-left: 1px solid #ddd;
   }

  &:after {
     content: '';
     display: table;
     clear: both;
   }
  }

  .horizontal {
  .org-tree-node {
  // display: flex;
  // flex-direction: row;
  // justify-content: flex-start;
  // align-items: center;
    display: table-cell;
    float: none;
    padding-top: 0;
    padding-left: 20px;

  &.is-leaf, &.collapsed {
                padding-top: 10px;
                padding-bottom: 10px;
              }

  &:before, &:after {
               width: 19px;
               height: 50%;
             }

  &:after {
     top: 50%;
     left: 0;
     border-left: 0;
   }

  &:only-child:before {
     top: 1px;
     border-bottom: 1px solid #ddd;
   }

  &:not(:first-child):before,
  &:not(:last-child):after {
     border-top: 0;
     border-left: 1px solid #ddd;
   }

  &:not(:only-child):after {
     border-top: 1px solid #ddd;
   }

  .org-tree-node-inner {
    display: table;
  }

  }

  .org-tree-node-label {
    display: table-cell;
    vertical-align: middle;
  }

  &.collapsable .org-tree-node.collapsed {
     padding-right: 30px;

  .org-tree-node-label:after {
    top: 0;
    left: 100%;
    width: 20px;
    height: 50%;
    border-right: 0;
    border-bottom: 1px solid #ddd;
  }
  }

  .org-tree-node-btn {
    top: 50%;
    left: 100%;
    margin-top: -11px;
    margin-left: 9px;
  }

  & > .org-tree-node:only-child:before {
      border-bottom: 0;
    }

  .org-tree-node-children {
  // display: flex;
  // flex-direction: column;
  // justify-content: center;
  // align-items: flex-start;
    display: table-cell;
    padding-top: 0;
    padding-left: 20px;

  &:before {
     top: 50%;
     left: 0;
     width: 20px;
     height: 0;
     border-left: 0;
     border-top: 1px solid #ddd;
   }

  &:after {
     display: none;
   }

  & > .org-tree-node {
      display: block;
    }
  }
  }
</style>
<style type="text/css">
  .org-tree-node-label {
    white-space: nowrap;
  }
  .bg-white {
    background-color: white;
  }
  .bg-black {
    background-color: #2F4056;
    color: #fff;
  }
  .bg-blue {
    background-color: #1E9FFF;
    color: #fff;
  }
  .bg-green {
    background-color: #009688;
    color: #fff;
  }
  .bg-orange {
    background-color: #FF5722;
    color: #fff;
  }
  .bg-yellow {
    background-color: #FFB800;
    color: #fff;
  }
</style>


