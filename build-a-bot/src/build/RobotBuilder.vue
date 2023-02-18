<template>
  <div>
    <div class="top-row">
      <div class="top part">
        <div class="robot-name">
          {{ selectedRobot.head.title }}
          <span v-if="selectedRobot.head.onSale" class="kaputt">kaputt!</span>
        </div>
        <img :src="selectedRobot.head.src" title="head" />
        <button @click="selectPreviousHead()" class="prev-selector">&#9668;</button>
        <button @click="selectNextHead()" class="next-selector">&#9658;</button>
      </div>
    </div>
    <div class="middle-row">
      <div class="left part">
        <img :src="selectedRobot.leftArm.src" title="left arm" />
        <button @click="selectPreviousLeftArm()" class="prev-selector">&#9650;</button>
        <button @click="selectNextLeftArm()" class="next-selector">&#9660;</button>
      </div>
      <div class="center part">
        <img :src="selectedRobot.torso.src" title="left arm" />
        <button class="prev-selector">&#9668;</button>
        <button class="next-selector">&#9658;</button>
      </div>
      <div class="right part">
        <img :src="selectedRobot.rightArm.src" title="left arm" />
        <button class="prev-selector">&#9650;</button>
        <button class="next-selector">&#9660;</button>
      </div>
    </div>
    <div class="bottom-row">
      <div class="bottom part">
        <img :src="selectedRobot.base.src" title="left arm" />
        <button class="prev-selector">&#9668;</button>
        <button class="next-selector">&#9658;</button>
      </div>
    </div>
  </div>
</template>

<script>
import availableParts from '../data/parts';

export default {
  name: 'RobotBuilder',
  data() {
    return {
      availableParts,
      selectedHeadIndex: 0,
      selectedLeftArmIndex: 0,
    };
  },
  computed: {
    selectedRobot() {
      return {
        head: this.availableParts.heads[this.selectedHeadIndex],
        leftArm: this.availableParts.arms[this.selectedLeftArmIndex],
        torso: this.availableParts.torsos[0],
        rightArm: this.availableParts.arms[0],
        base: this.availableParts.bases[0],
      };
    },
  },
  methods: {
    selectNextHead() {
      if (this.selectedHeadIndex + 1 < this.availableParts.heads.length) {
        this.selectedHeadIndex += 1;
      }
    },
    selectPreviousHead() {
      if (this.selectedHeadIndex - 1 >= 0) {
        this.selectedHeadIndex -= 1;
      }
      console.log(`selectedHeadIndex: ${this.selectedHeadIndex}`);
    },
    selectNextLeftArm() {
      if (this.selectedLeftArmIndex + 1 < this.availableParts.arms.length) {
        this.selectedLeftArmIndex += 1;
      }
    },
    selectPreviousLeftArm() {
      if (this.selectedLeftArmIndex - 1 >= 0) {
        this.selectedLeftArmIndex -= 1;
      }
      console.log(`selectedLeftArmIndex: ${this.selectedLeftArmIndex}`);
    },
  },
};
</script>
<style>
.robot-name {
  position: absolute;
  top: -80px;
  left: 0;
  width: 100%;
  text-align: center;
  background-color: rgba(0, 0, 0, 0.5);
  color: white;
  font-size: 1.5em;
  padding: 5px;
}

.kaputt {
  color: red;
  transition: all 0.5s ease-in-out;
}

.kaputt:hover {
  font-size: larger;
}

.part {
  position: relative;
  width: 165px;
  height: 165px;
  border: 3px solid #aaa;
}
.part img {
  width: 165px;
}
.top-row {
  display: flex;
  justify-content: space-around;
}
.middle-row {
  display: flex;
  justify-content: center;
}
.bottom-row {
  display: flex;
  justify-content: space-around;
  border-top: none;
}
.head {
  border-bottom: none;
}
.left {
  border-right: none;
}
.right {
  border-left: none;
}
.left img {
  transform: rotate(-90deg);
}
.right img {
  transform: rotate(90deg);
}
.bottom {
  border-top: none;
}
.prev-selector {
  position: absolute;
  z-index: 1;
  top: -3px;
  left: -28px;
  width: 25px;
  height: 171px;
}
.next-selector {
  position: absolute;
  z-index: 1;
  top: -3px;
  right: -28px;
  width: 25px;
  height: 171px;
}
.center .prev-selector,
.center .next-selector {
  opacity: 0.8;
}
.left .prev-selector {
  top: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}
.left .next-selector {
  top: auto;
  bottom: -28px;
  left: -3px;
  width: 144px;
  height: 25px;
}
.right .prev-selector {
  top: -28px;
  left: 24px;
  width: 144px;
  height: 25px;
}
.right .next-selector {
  top: auto;
  bottom: -28px;
  left: 24px;
  width: 144px;
  height: 25px;
}
.right .next-selector {
  right: -3px;
}
</style>
