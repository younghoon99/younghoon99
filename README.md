<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=Venom&color=0:6c5ce7,100:a29bfe&height=300&section=header&text=Development%20Log&fontSize=70&animation=twinkling&fontColor=e9e1ff&fontAlignY=40&desc=Unity%20VR%20Developer%20Portfolio&descSize=25&descAlignY=60&stroke=483d8b&strokeWidth=1" />
</div>

##
<br><br>
<div align="center">
  <h3>
   "As a developer specializing in immersive game development using Unity and VR,<br>
I am dedicated to building richer and more engaging virtual worlds."
  </h3>
</div>
<br><br>

## 📊 Profile

<div align="center">

**EMail: dladudgns321@naver.com**
<br><br>

<a href="https://blog.naver.com/y_oung99">
  <img src="https://play-lh.googleusercontent.com/rdmNKWDpwdzP-UBlrKQqVWwOm0vnvXg8lOD4vRQJQm8AR2lK2BBAGbrPzlDfI9lWyQ" width="40" alt="Blog"/>
</a>
&nbsp;&nbsp;
<a href="https://www.instagram.com/y___oung99">
  <img src="https://cdn-icons-png.flaticon.com/512/1384/1384063.png" width="40" alt="Instagram"/>
</a>
&nbsp;&nbsp;
<a href="https://www.youtube.com/@%EC%B4%88%EC%BD%94-v7b">
  <img src="https://littledeep.com/wp-content/uploads/2020/09/youtube-icon-style.png" width="40" alt="YouTube"/>
</a>
&nbsp;&nbsp;
<a href="https://www.notion.so/1c1ddb27d189802a9aa4f18bfff87027?pvs=4">
  <img src="https://noticon-static.tammolo.com/dgggcrkxq/image/upload/v1566778642/noticon/kjaaizycfgz017qxvlnu.png" width="40" alt="Notion"/>
</a>

</div>





## 🔧 Tech Stack & Tools

<div align="center">
  <h3>🎮 Game Development</h3>
  <img src="https://img.shields.io/badge/Unity-000000?style=for-the-badge&logo=Unity&logoColor=white"/>
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=CSharp&logoColor=white"/>
  <img src="https://img.shields.io/badge/Unity%20XR-000000?style=for-the-badge&logo=Unity&logoColor=white"/>
  <img src="https://img.shields.io/badge/VRChat%20SDK-000000?style=for-the-badge&logo=VRChat&logoColor=white"/>
  <img src="https://img.shields.io/badge/Oculus%20Integration-1C1E20?style=for-the-badge&logo=Oculus&logoColor=white"/>
  <br>
  <img src="https://img.shields.io/badge/Unity%20Shader%20Graph-000000?style=for-the-badge&logo=Unity&logoColor=white"/>
  <img src="https://img.shields.io/badge/Photon%20Networking-00ADEF?style=for-the-badge&logo=Photon&logoColor=white"/>
  <img src="https://img.shields.io/badge/UdonSharp-5865F2?style=for-the-badge&logo=VRChat&logoColor=white"/>
  
  <h3>🎨 Design & 3D Modeling</h3>
  <img src="https://img.shields.io/badge/Blender-F5792A?style=for-the-badge&logo=Blender&logoColor=white"/>
  <img src="https://img.shields.io/badge/Photoshop-31A8FF?style=for-the-badge&logo=Adobe%20Photoshop&logoColor=white"/>
  <img src="https://img.shields.io/badge/Figma-F24E1E?style=for-the-badge&logo=Figma&logoColor=white"/>
 
  
  <h3>🛠️ Collaboration</h3>
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=GitHub&logoColor=white"/>
  <img src="https://img.shields.io/badge/Notion-000000?style=for-the-badge&logo=Notion&logoColor=white"/>
</div>


## 🎮 Project Gallery

<table>
   <tr>
    <td width="40%">
      <a href="https://youtu.be/zwbzy_umyso">
        <img src="https://www.notion.so/image/attachment%3Ad6ceb84c-623b-4c2c-9394-9555ffa3c87e%3A%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2025-05-27_173703.png?table=block&id=200ddb27-d189-804f-8162-f6c958d2bf56&spaceId=6b98e78d-cc49-47f6-a0bf-9b1b0470f6ac&width=1420&userId=&cache=v2" width="100%" alt="버그를 찾아라"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🌟 버그를 찾아라 (2025.05.14 ~ 2025.05.21)</h3>
      <p>VRChat SDK와 UdonSharp을 활용하여 "숨어라 벌레잡기" 비대칭 멀티플레이어 게임을 설계·구현했습니다.</p>
      <a href="https://github.com/younghoon99/BugGame" target="_blank">
  <img src="https://img.shields.io/badge/버그 찾기 게임으로 이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      <details>
        <summary>⭐팀 배정</summary>
   
```csharp
/// <summary>
/// 플레이어 팀 배정 (마스터 클라이언트에서만 호출)
/// </summary>
public void AssignTeams()
{
    // 마스터 클라이언트만 실행
    if (!Utilities.IsValid(localPlayer) || !localPlayer.isMaster) return;

    // 플레이어 목록 가져오기
    VRCPlayerApi[] players = new VRCPlayerApi[VRCPlayerApi.GetPlayerCount()];
    players = VRCPlayerApi.GetPlayers(players);
    playerCount = players.Length;

    // 팀 배정 초기화
    for (int i = 0; i < playerTeams.Length; i++)
    {
        playerTeams[i] = -1; // 미배정 상태로 초기화
    }

    // 최소 인원 체크
    if (playerCount < minTotalPlayers)
    {
        Debug.Log("플레이어 수가 부족합니다. 최소 " + minTotalPlayers + "명 필요");
        return;
    }

    // 사냥꾼 팀 배정 (1명)
    int hunterIndex = UnityEngine.Random.Range(0, playerCount);
    playerTeams[players[hunterIndex].playerId] = TEAM_HUNTER;

    // 나머지 플레이어는 벌레 팀으로 배정
    for (int i = 0; i < playerCount; i++)
    {
        if (i != hunterIndex)
        {
            playerTeams[players[i].playerId] = TEAM_BUG;
        }
    }

    // 로컬 플레이어 팀 설정
    localPlayerTeam = playerTeams[localPlayerId];

    // 네트워크 동기화
    RequestSerialization();

    Debug.Log("팀 배정 완료: 사냥꾼 " + players[hunterIndex].displayName + ", 벌레 " + (playerCount - 1) + "명");
}
```
</details>


 <details>
        <summary>🔨망치 타격 시스템</summary>
   
```csharp
// 트리거 충돌 감지
private void OnTriggerEnter(Collider other)
{
    if (!Utilities.IsValid(localPlayer) || !Utilities.IsValid(checkPlayer)) return;
    
    // 망치가 휘두르는 중이 아니면 충돌 무시
    if (!isSwinging) return;
    
    Debug.Log("망치 충돌 감지");
    
    // 충돌 위치 계산
    Vector3 hitPosition = other.ClosestPoint(transform.position);
    
    // 타격 효과 표시 (있는 경우)
    ShowHitEffect(hitPosition);
    
    // 테스트용 벌레 오브젝트 감지 추가
    TestBug testBug = other.GetComponent<TestBug>();
    if (testBug != null)
    {
        Debug.Log("테스트 벌레 오브젝트를 타격했습니다!");
        
        // 타격 효과음 재생
        PlayHitSound();
        
        // 테스트 벌레 오브젝트에 타격 이벤트 전달
        testBug.OnHit();
        return;
    }
    
    // 모든 플레이어 가져오기
    VRCPlayerApi[] players = new VRCPlayerApi[VRCPlayerApi.GetPlayerCount()];
    VRCPlayerApi.GetPlayers(players);
    
    // 모든 플레이어에 대해 거리 계산
    foreach (var player in players)
    {
        if (!Utilities.IsValid(player)) continue;
        
        // 플레이어의 위치와 충돌 지점의 거리 확인
        float distance = Vector3.Distance(player.GetPosition(), hitPosition);
        
        if (distance < hitRadius) // 설정된 타격 감지 반경 내에 있는지 확인
        {
            Debug.Log("플레이어가 타격 범위 내에 있습니다. 거리: " + distance);
            
            // CheckPlayer를 통해 팀 확인
            int playerTeam = checkPlayer.GetPlayerTeam(player.playerId);
            Debug.Log("플레이어의 팀: " + playerTeam);
            
            if (playerTeam == CheckPlayer.TEAM_BUG) // 벌레 팀인 경우
            {
                Debug.Log("벌레 팀 플레이어를 타격했습니다!");
                
                // 타격 효과음 재생 (있는 경우)
                PlayHitSound();
                
                // 네트워크 소유자인 경우에만 탈락 처리 (마스터 클라이언트)
                if (Networking.IsMaster)
                {
                    // 벌레 팀 플레이어 탈락 처리
                    checkPlayer.EliminatePlayer(player.playerId);
                    
                    // GameManager에 탈락 이벤트 전달
                    if (gameManager != null)
                    {
                        gameManager.OnPlayerEliminated(player.playerId);
                    }
                    
                    Debug.Log("플레이어가 탈락 처리되었습니다.");
                }
            }
        }
    }
}
```
</details>
 <details>
        <summary>🎰게임 승리 조건 및 결과 처리</summary>
   
```csharp
/// <summary>
/// 플레이어 탈락 처리 (HammerController에서 호출)
/// </summary>
public void OnPlayerEliminated(int playerId)
{
    if (!localPlayer.isMaster) return;

    // 탈락한 플레이어가 벌레 팀인지 확인
    if (checkPlayer.GetPlayerTeam(playerId) == TEAM_BUG)
    {
        // 살아있는 벌레 수 감소
        aliveBugCount--;

        // 벌레가 모두 탈락하면 사냥꾼 팀 승리
        if (aliveBugCount <= 0)
        {
            EndGame(WINNER_HUNTER);
        }

        // 네트워크 동기화
        RequestSerialization();

        // 전체 플레이어에게 상태 알림
        SendCustomNetworkEvent(VRC.Udon.Common.Interfaces.NetworkEventTarget.All, "UpdateGameStatusText");

        Debug.Log("벌레 팀 플레이어 탈락: 남은 벌레 " + aliveBugCount + "명");
    }
}

/// <summary>
/// 게임 결과 표시
/// </summary>
private void ShowGameResult()
{
    // 승리 패널 활성화
    if (winnerPanel != null)
    {
        winnerPanel.SetActive(true);
    }

    // 승리 팀 텍스트 설정
    if (winnerText != null)
    {
        if (winnerTeam == WINNER_HUNTER)
        {
            winnerText.text = "사냥꾼 팀 승리!\n모든 벌레를 잡았습니다.";
            winnerText.color = new Color(1f, 0.5f, 0f); // 주황색
        }
        else if (winnerTeam == WINNER_BUG)
        {
            winnerText.text = "벌레 팀 승리!\n시간 내에 살아남았습니다.";
            winnerText.color = new Color(0.2f, 0.8f, 0.2f); // 초록색
        }
    }

    // 게임 상태 텍스트 업데이트
    UpdateGameStatusText();

    // 5초 후 로비로 돌아가기
    SendCustomEventDelayedSeconds("ReturnToLobby", 5.0f);
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/네트워크-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/미니게임-5bc0de?style=flat-square"/>
        <img src="https://img.shields.io/badge/술래잡기-d9534f?style=flat-square"/>
      </div>
    </td>
  </tr>
  
  <tr>
    <td width="40%">
      <a href="https://youtu.be/5FuCTJ1qK3s">
        <img src="https://www.notion.so/image/attachment%3A043cdd30-3adb-4c0c-8afe-202fe10264cc%3Aimage.png?table=block&id=1dfddb27-d189-805c-86d3-ea0dd317d05a&spaceId=6b98e78d-cc49-47f6-a0bf-9b1b0470f6ac&width=1420&userId=&cache=v2" width="100%" alt="캠프파이어 맵"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🌟 VRChat 캠프파이어 맵 (2025.02.04 ~ 🔥)</h3>
      <p>실시간 네트워크 동기화와 파티클 시스템을 활용한 몽환적인 캠프파이어 맵입니다. UdonSynced와 소유권 관리 시스템으로 모든 오브젝트 상태가 실시간으로 동기화됩니다.</p>
      <a href="https://github.com/younghoon99/_Camp" target="_blank">
  <img src="https://img.shields.io/badge/캠프파이어_World로_이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      <details>
        <summary>💧물 속 효과</summary>
   
```csharp
using UdonSharp;
using UnityEngine;
using VRC.SDKBase;

public class UnderWater : UdonSharpBehaviour
{
    public AudioSource audioSource;
    private bool isPlayerInWater = false;

    [Header("포스트 프로세싱 설정")]
    public GameObject normalPostProcessing;
    public GameObject underwaterPostProcessing;

    private void UpdatePostProcessing()
    {
        if (normalPostProcessing != null && underwaterPostProcessing != null)
        {
            normalPostProcessing.SetActive(!isPlayerInWater);
            underwaterPostProcessing.SetActive(isPlayerInWater);
        }
    }

    public override void OnPlayerTriggerEnter(VRCPlayerApi player)
    {
        if (player.isLocal)
        {
            isPlayerInWater = true;
            if (audioSource != null && !audioSource.isPlaying)
            {
                audioSource.Play();
            }
            UpdatePostProcessing();
        }
    }

    public override void OnPlayerTriggerExit(VRCPlayerApi player)
    {
        if (player.isLocal)
        {
            isPlayerInWater = false;
            if (audioSource != null && audioSource.isPlaying)
            {
                audioSource.Stop();
            }
            UpdatePostProcessing();
        }
    }
}
```
</details>


 <details>
        <summary>🔥캠프 불 동기화</summary>
   
```csharp
using UdonSharp;
using UnityEngine;
using VRC.SDKBase;
using VRC.Udon;

[UdonBehaviourSyncMode(BehaviourSyncMode.Manual)]
public class FireTrigger : UdonSharpBehaviour
{
    public GameObject Fire;
   
    [UdonSynced]
    private bool isActive;

    public bool IsActive
    {
        get => isActive;
        set
        {
            isActive = value;
            if (Fire != null)
            {
                Fire.SetActive(isActive);
            }
        }
    }

    public override void Interact()
    {
        if (Networking.IsOwner(gameObject))
        {
            IsActive = !IsActive;
            RequestSerialization();
        }
        else
        {
            Networking.SetOwner(Networking.LocalPlayer, gameObject);
            SendCustomNetworkEvent(VRC.Udon.Common.Interfaces.NetworkEventTarget.Owner, nameof(Interact));
        }
    }

    public override void OnDeserialization()
    {
        if (Fire != null)
        {
            Fire.SetActive(isActive);
        }
    }
}
```
</details>
 <details>
        <summary>🔊월드 사운드</summary>
   
```csharp
using UdonSharp;
using UnityEngine;
using VRC.SDKBase;

public class WorldSound : UdonSharpBehaviour
{
    [Header("소리 설정")]
    [Tooltip("소리를 재생할 오브젝트")]
    public GameObject Sound;

    [Header("소리 범위 설정")]
    [Tooltip("소리가 최대 볼륨으로 들리는 거리")]
    public float minDistance = 1f;

    [Tooltip("소리가 들리는 최대 거리")]
    public float maxDistance = 10f;

    [Tooltip("소리 볼륨")]
    [Range(0f, 1f)]
    public float volume = 1f;

    private AudioSource audioSource;

    private void Start()
    {
        if (Sound != null)
        {
            audioSource = Sound.GetComponent<AudioSource>();
            ApplySoundSettings();
        }
    }

    public void ApplySoundSettings()
    {
        if (audioSource != null)
        {
            audioSource.minDistance = minDistance;
            audioSource.maxDistance = maxDistance;
            audioSource.volume = volume;
            audioSource.spatialBlend = 1f; // 3D 사운드로 설정
        }
    }

    public override void Interact()
    {
        if (audioSource == null && Sound != null)
        {
            audioSource = Sound.GetComponent<AudioSource>();
            ApplySoundSettings();
        }

        if (audioSource != null)
        {
            if (audioSource.isPlaying)
            {
                audioSource.Stop();
            }
            else
            {
                audioSource.Play();
            }
        }
    }

    // 에디터에서 값이 변경될 때 호출
    private void OnValidate()
    {
        if (Application.isPlaying && audioSource != null)
        {
            ApplySoundSettings();
        }
    }
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/네트워크-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/파티클-5bc0de?style=flat-square"/>
        <img src="https://img.shields.io/badge/효과-d9534f?style=flat-square"/>
      </div>
    </td>
  </tr>
  
  <tr>
    <td width="40%">
      <a href="https://youtu.be/SFu2kHuo2Yw">
        <img src="https://www.notion.so/image/attachment%3Ac019b766-3481-4ee3-82d2-9d758319388e%3Aimage.png?table=block&id=1dfddb27-d189-808f-9b91-c0fb940fc6b4&spaceId=6b98e78d-cc49-47f6-a0bf-9b1b0470f6ac&width=1420&userId=&cache=v2" width="100%" alt="공포 월드"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🌑 VRChat 공포 월드 (2025.01.15 ~ 2025.01.31)</h3>
      <p>긴장감 넘치는 공포 체험을 제공하는 VRChat 월드입니다. 다양한 트리거와 이벤트로 사용자에게 몰입감 있는 경험을 선사합니다.</p>
      <a href="https://github.com/younghoon99/_horror" target="_blank">
  <img src="https://img.shields.io/badge/공포_World로_이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      <details>
        <summary>💀점프스케어 관리 </summary>
   
```csharp
public class JumpscareController : UdonSharpBehaviour
{
    [Header("UI 설정")]
    public Canvas jumpscareCanvas;
    public Image jumpscareImage;
    public float imageDuration = 1f;     // 이미지 표시 총 시간
    public float fadeInDuration = 0.1f;  // 페이드 인에 걸리는 시간
    public float fadeOutDuration = 0.2f; // 페이드 아웃에 걸리는 시간

    [Header("사운드 설정")]
    public AudioSource jumpscareSound;
    
    private bool isJumpscareActive = false;
    private float timer = 0f;

    private void TriggerJumpscare()
    {
        isJumpscareActive = true;
        timer = 0f;

        // 캔버스 활성화 및 이미지 초기화
        if (jumpscareCanvas != null)
        {
            jumpscareCanvas.gameObject.SetActive(true);
            
            if (jumpscareImage != null)
            {
                // 시작 시 완전히 투명하게 설정
                Color imageColor = jumpscareImage.color;
                imageColor.a = 0f;
                jumpscareImage.color = imageColor;
            }
        }

        // 사운드 재생
        if (jumpscareSound != null)
        {
            jumpscareSound.Play();
        }
    }
}
```
</details>
<details>
        <summary>🎬컷신 관리  </summary>
   
```csharp
public class CutsceneController : UdonSharpBehaviour
{
    [Header("컷신 기본 설정")]
    public Camera cutsceneCamera;           // 컷신용 카메라
    public float cinematicDuration = 20f;   // 전체 컷신 지속 시간
    
    [Header("컷신 이벤트 컨트롤러")]
    public AudioSource sound1;              // 사운드 효과
    public GameObject[] ghostObjects;        // 귀신 오브젝트들
    
    [Header("컷신용 조명 설정")]
    public Light finalPointLight;           // 마지막에 비출 PointLight
    
    private bool isPlaying = false;
    private float timer = 0f;
    private VRCPlayerApi localPlayer;
    private int currentPhase = 0;           // 현재 페이즈
    
    public override void OnPlayerTriggerEnter(VRCPlayerApi player)
    {
        if (player == Networking.LocalPlayer && !isPlaying)
        {
            StartCinematic();
        }
    }
    
    public void StartCinematic()
    {
        isPlaying = true;
        timer = 0f;
        currentPhase = 0;
        
        // 플레이어 이동 제한
        if(localPlayer != null)
        {
            localPlayer.Immobilize(true);
        }
        
        // 컷신 카메라 활성화
        if(cutsceneCamera != null)
        {
            cutsceneCamera.enabled = true;
        }
    }
    
    private void SetAllGhostsActive(bool active)
    {
        if (ghostObjects == null) return;
        
        for(int i = 0; i < ghostObjects.Length; i++)
        {
            if(ghostObjects[i] != null)
                ghostObjects[i].SetActive(active);
        }
    }
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/네트워크-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/호러게임-5bc0de?style=flat-square"/>
        <img src="https://img.shields.io/badge/공포체험-d9534f?style=flat-square"/>
      </div>
    </td>
  </tr>
  
  <tr>
    <td width="40%">
      <a href="https://youtu.be/pIG3t2twTZ4">
        <img src="https://github.com/user-attachments/assets/a4f4ec45-076d-435a-8d74-d694efe7d1cb" width="100%" alt="RPG 프로토타입"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🎯 RPG 프로토타입 (2025.04.30 ~ 2025.05.13)</h3>
      <p>Unity 6 환경에서 1인 개발한 액션 RPG 프로토타입입니다. 검기 이펙트 시스템, JSON 기반 스킬 시스템, 오브젝트 풀링 최적화 등을 구현했습니다.</p>
      <a href="https://github.com/younghoon99/_RPG" target="_blank">
  <img src="https://img.shields.io/badge/RPG로_이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      <details>
        <summary>🛜JSON 기반 스킬 시스템 </summary>
   
```csharp
public class SkillLoader : MonoBehaviour
{
    public static SkillLoader skillLoader;
    public List<Skill> skill;

    void LoadSkills()
    {
        TextAsset jsonFile = Resources.Load<TextAsset>("skill");
        if (jsonFile != null)
        {
            skill = new List<Skill>(JsonHelper.FromJson<Skill>(jsonFile.text));
            Debug.Log("스킬 개수: " + skill.Count);
            Debug.Log("첫번째 스킬 이름: " + skill[0].name);
        }
        else
        {
            Debug.LogError("skills.json 파일을 찾을 수 없습니다.");
        }
    }
}

[System.Serializable]
public class Skill
{
    public string name;
    public int damage;
    public float cooldown;
}
```
</details>

<details>
        <summary>⚔️오브젝트 풀링 검기 시스템   </summary>
   
```csharp
public class SlashController : MonoBehaviour
{
    public GameObject[] slashPrefabs;  // 사용할 검기 이펙트 프리팹들
    public Transform[] slashPositions;  // 각 검기 이펙트의 생성 위치/방향
    public int currentSlashIndex = 0;
    
    [Header("오브젝트 풀링 설정")]
    public int poolSize = 5;
    public bool autoExpand = true;
    
    private Dictionary<int, List<GameObject>> slashPools;

    private void InitializeObjectPools()
    {
        slashPools = new Dictionary<int, List<GameObject>>();
        
        // 각 프리팹 타입별로 풀 생성
        for (int i = 0; i < slashPrefabs.Length; i++)
        {
            if (slashPrefabs[i] == null) continue;
            
            List<GameObject> pool = new List<GameObject>();
            slashPools[i] = pool;
            
            // 풀 사이즈만큼 오브젝트 미리 생성
            for (int j = 0; j < poolSize; j++)
            {
                CreateNewSlashInstance(i);
            }
        }
    }
    
    // 풀에서 사용 가능한 오브젝트 가져오기
    private GameObject GetSlashFromPool(int prefabIndex)
    {
        if (!slashPools.ContainsKey(prefabIndex))
        {
            slashPools[prefabIndex] = new List<GameObject>();
            for (int i = 0; i < poolSize; i++)
            {
                CreateNewSlashInstance(prefabIndex);
            }
        }
        
        List<GameObject> pool = slashPools[prefabIndex];
        
        // 비활성화된 오브젝트 찾기
        foreach (GameObject slash in pool)
        {
            if (slash != null && !slash.activeInHierarchy)
            {
                return slash;
            }
        }
        
        // 자동 확장이 활성화된 경우
        if (autoExpand)
        {
            return CreateNewSlashInstance(prefabIndex);
        }
        
        return null;
    }
}
```
</details>

<details>
        <summary>🤺콤보 공격 시스템   </summary>
   
```csharp
public class Player : MonoBehaviour
{
    private bool _isAttacking = false;
    private Animator animator;
    private bool canCombo = true;
    private float lastComboTime = 0f;
    
    int hashAttackCount = Animator.StringToHash("AttackCount");
    
    public int AttackCount
    {
        get => animator.GetInteger(hashAttackCount);
        set => animator.SetInteger(hashAttackCount, value);
    }

    void Update()
    {
        // 콤보 타이머 처리: 일정 시간 동안 다음 콤보 입력이 없으면 공격 상태 종료
        if (isAttacking && canCombo && Time.time - lastComboTime > comboTimeout)
        {
            isAttacking = false;
            AttackCount = 0;
            canCombo = true;
        }

        // 공격 입력 처리 (마우스 좌클릭)
        if (Input.GetMouseButtonDown(0))
        {
            if (!isAttacking)
            {
                // 첫 번째 공격 시작
                isAttacking = true;
                AttackCount = 1;
                animator.SetTrigger("Attack");
                canCombo = false;
            }
            else if (canCombo)
            {
                // 콤보 공격 (다음 단계로 진행)
                int nextAttack = AttackCount + 1;
                if (nextAttack <= 3)  // 최대 3단계 콤보
                {
                    AttackCount = nextAttack;
                    animator.SetTrigger("Attack");
                    canCombo = false;
                }
            }
        }
    }
    
    // 마지막 콤보 애니메이션이 끝날 때 호출될 이벤트 함수
    public void OnAttackAnimationEnd()
    {
        isAttacking = false;
        AttackCount = 0;
        canCombo = true;
    }

    // 중간 콤보 애니메이션이 끝날 때 호출될 이벤트 함수
    public void OnComboAnimationEnd()
    {
        canCombo = true;
        lastComboTime = Time.time;
    }
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/RPG-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/1인개발-f0ad4e?style=flat-square"/>
      </div>
    </td>
  </tr>
  
  <tr>
    <td width="40%">
      <a href="https://youtu.be/Tnn4wbkD6_E">
        <img src="https://www.notion.so/image/attachment%3A5c5b2d54-3a3f-40ef-82b9-bf9870f9fea2%3A%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2025-04-29_171134.png?table=block&id=1e4ddb27-d189-80a2-99f0-c94d306abf57&spaceId=6b98e78d-cc49-47f6-a0bf-9b1b0470f6ac&width=1420&userId=&cache=v2" width="100%" alt="대전 게임"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🎮 대전 프로젝트 Versus (2025.04.12 ~ 2025.04.30)</h3>
      <p>귀여운 캐릭터들의 대전 게임입니다. Photon을 통해 실시간 네트워크 시스템 구현, 채팅 구현을 했습니다 .</p>
      <a href="https://github.com/younghoon99/Versus" target="_blank">
  <img src="https://img.shields.io/badge/Versus로_이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      
<details>
        <summary>🖥️포톤 네트워크 채팅 시스템   </summary>
   
```csharp
public class ChatManager : MonoBehaviourPunCallbacks
{
    // 싱글톤 인스턴스 (전역 접근용)
    public static ChatManager Instance { get; private set; }
    public GameObject m_Content;
    public GameObject chatTextPrefab;
    public TMP_InputField m_inputField;
    public ScrollRect scrollRect;
    
    PhotonView photonview;
    
    // 입력 필드에서 엔터 키를 눌렀을 때 호출
    public void OnEndEditEvent()
    {
        if (Input.GetKeyDown(KeyCode.Return))
        {
            string nickname = GetCharacterNickname();
            string strMessage = nickname + " : " + m_inputField.text;
            photonview.RPC("RPC_Chat", RpcTarget.All, strMessage);
            m_inputField.text = "";
        }
    }
    
    // 캐릭터 ID에 따라 닉네임 반환
    string GetCharacterNickname()
    {
        string nickname = "알수없음";
        if (Photon.Pun.PhotonNetwork.LocalPlayer.CustomProperties.ContainsKey("CharacterSelection"))
        {
            int charId = (int)Photon.Pun.PhotonNetwork.LocalPlayer.CustomProperties["CharacterSelection"];
            if (charId == 0) nickname = "노랭이";
            else if (charId == 1) nickname = "파랭이";
        }
        return nickname;
    }
    
    // RPC로 호출되는 채팅 함수 (모든 클라이언트에서 실행)
    [PunRPC]
    void RPC_Chat(string message)
    {
        // 받은 메시지를 UI에 추가
        AddChatMessage(message);
    }
}
```
</details>

<details>
        <summary>💫플레이어 충돌 및 스턴 시스템   </summary>
   
```csharp
public class Player : MonoBehaviour
{
    private Rigidbody rb;
    private bool canMove = true;
    private bool isStuned = false;
    private bool wasStuned = false;
    private float pushForce;
    private Vector3 pushDir;
    
    /// <summary>
    /// 플레이어를 스턴 상태로 만들고 특정 방향으로 밀어내는 함수
    /// </summary>
    /// <param name="velocityF">밀어내는 방향과 힘을 결합한 벡터</param>
    /// <param name="time">스턴 지속 시간 (초)</param>
    public void HitPlayer(Vector3 velocityF, float time)
    {
        // 스턴 상태 설정
        isStuned = true;
        canMove = false;
        
        // 밀려나는 힘과 방향 설정
        pushForce = velocityF.magnitude;
        pushDir = Vector3.Normalize(velocityF);
        
        // 현재 수직 속도 유지하며 수평 방향만 설정
        Vector3 currentVelocity = rb.velocity;
        rb.velocity = new Vector3(velocityF.x, currentVelocity.y, velocityF.z);
        
        // 스턴 효과 적용 코루틴 시작
        StartCoroutine(Decrease(velocityF.magnitude, time));
        
        // 히트 사운드 재생
        AudioSource.PlayClipAtPoint(HitSound, transform.position, 2f);
    }
    
    /// <summary>
    /// 스턴 효과를 일정 시간 동안 적용하고 점차 감소시키는 코루틴
    /// </summary>
    private IEnumerator Decrease(float value, float duration)
    {
        // 현재 스턴 상태에서 중첩 스턴이 들어온 경우
        if (isStuned)
            wasStuned = true;
            
        // 지속 시간 동안 힘 감소율 계산
        float delta = value / duration;
        
        // 지정된 시간 동안 힘 감소
        for (float t = 0; t < duration; t += Time.deltaTime)
        {
            yield return null;
            
            // 일반 바닥에서는 힘 감소
            pushForce = pushForce - Time.deltaTime * delta;
            pushForce = pushForce < 0 ? 0 : pushForce;
        }
        
        // 중첩 스턴이 아닌 경우 스턴 해제
        if (!wasStuned)
        {
            isStuned = false;
            canMove = true;
        }
        else
        {
            wasStuned = false;
        }
    }
}
```
</details>

<details>
        <summary>😶멀티플레이어 캐릭터 생성 시스템   </summary>
   
```csharp
public class PlayerManager : MonoBehaviourPunCallbacks
{
    [SerializeField] private GameObject[] characterPrefabs = new GameObject[2];
    [SerializeField] private Transform character1SpawnPoint;
    [SerializeField] private Transform character2SpawnPoint;
    
    private readonly string CHARACTER_SELECTION_PROP = "CharacterSelection";
    
    // 플레이어 캐릭터 생성 메서드
    private void SpawnPlayer()
    {
        // 캐릭터 ID 가져오기
        int characterID = 0;
        
        if (PlayerPrefs.HasKey(CHARACTER_PREFS_KEY))
        {
            characterID = PlayerPrefs.GetInt(CHARACTER_PREFS_KEY);
        }
        else if (PhotonNetwork.LocalPlayer.CustomProperties.TryGetValue(CHARACTER_SELECTION_PROP, out object characterObj))
        {
            characterID = (int)characterObj;
        }
        
        // 캐릭터 ID에 따른 스폰 위치 결정
        Vector3 spawnPosition = Vector3.zero;
        Quaternion spawnRotation = Quaternion.identity;
        
        switch (characterID)
        {
            case 0: // Character1 스폰 위치
                if (character1SpawnPoint != null)
                {
                    spawnPosition = character1SpawnPoint.position;
                    spawnRotation = character1SpawnPoint.rotation;
                }
                break;
                
            case 1: // Character2 스폰 위치
                if (character2SpawnPoint != null)
                {
                    spawnPosition = character2SpawnPoint.position;
                    spawnRotation = character2SpawnPoint.rotation;
                }
                break;
        }
        
        // 네트워크를 통해 플레이어 생성
        string prefabName = characterPrefabs[characterID].name;
        GameObject playerObj = PhotonNetwork.Instantiate(prefabName, spawnPosition, spawnRotation);
        
        // 카메라 및 컨트롤 설정
        SetupPlayerCamera(playerObj);
    }
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/pvp-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/아트워크-f0ad4e?style=flat-square"/>
        <img src="https://img.shields.io/badge/3D-d9534f?style=flat-square"/>
      </div>
    </td>
  </tr>
  
  <tr>
    <td width="40%">
      <a href="https://youtu.be/0hPzJI-Z2zI">
        <img src="https://www.notion.so/image/attachment%3Af3bfd331-cf92-4ab9-b982-6848641350fc%3Aimage.png?table=block&id=1dfddb27-d189-8031-a245-db37aa202e1f&spaceId=6b98e78d-cc49-47f6-a0bf-9b1b0470f6ac&width=1420&userId=&cache=v2" width="100%" alt="타운 프로젝트"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🏰 타운 프로젝트 Long live town (2025.03.22 ~ 2025.04.22)</h3>
      <p>생존과 마을 디펜스 요소를 결합한 2D 게임입니다. 자원 관리, 타워 건설, 적 방어 시스템을 구현했습니다.</p>
      <a href="https://github.com/younghoon99/LongLiveTown" target="_blank">
  <img src="https://img.shields.io/badge/LongLiveTown로_이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      
<details>
        <summary>🧟적 체력 및 데미지 시스템    </summary>
   
```csharp
public class EnemyHealth : MonoBehaviour
{
    [Header("체력 설정")]
    public float maxHealth = 100f;      // 최대 체력
    public float currentHealth;         // 현재 체력
    
    [Header("UI 설정")]
    public Image healthBarImage;        // 체력바 이미지
    public float smoothSpeed = 5f;      // 체력바 변화 속도
    public GameObject floatingDamageTextPrefab; // 데미지 텍스트 프리팹
    
    // 데미지 처리 함수
    public void TakeDamage(float damage, Vector2 hitPosition = default)
    {
        // 죽었거나 무적 상태면 데미지를 받지 않음
        if (isDead || isInvincible) return;
        
        // 체력 감소
        currentHealth = Mathf.Max(0, currentHealth - damage);
        
        // 데미지 텍스트 생성
        ShowDamageText(damage);
        
        // 체력바 업데이트
        UpdateHealthBar();
        
        // 사망 체크
        if (currentHealth <= 0)
        {
            Die();
        }
        else
        {
            // 무적 시간 및 깜빡임 효과 적용
            StartCoroutine(InvincibilityCoroutine());
        }
    }
    
    // 데미지 텍스트 표시 함수
    private void ShowDamageText(float damage)
    {
        // 데미지 텍스트 생성 및 애니메이션 처리
        if (floatingDamageTextPrefab != null)
        {
            GameObject textObj = Instantiate(floatingDamageTextPrefab, transform.position + Vector3.up, Quaternion.identity);
            TextMeshProUGUI tmpText = textObj.GetComponent<TextMeshProUGUI>();
            if (tmpText != null)
            {
                tmpText.text = damage.ToString("0");
                StartCoroutine(AnimateDamageText(textObj));
            }
        }
    }
}
```
</details>

<details>
        <summary>💬플레이어 공격 및 상호작용 시스템   </summary>
   
```csharp
public class Player : MonoBehaviour
{
    // 현재 플레이어가 장착한 아이템
    public Item equippedItem;
    
    // 공격 설정
    [Header("공격 설정")]
    private float attackDamage;      
    [SerializeField] private float attackRange = 1.5f;
    [SerializeField] private Transform attackPoint;
    
    // 외부에서 장착 아이템을 세팅하는 함수
    public void SetEquippedItem(Item item)
    {
        equippedItem = item;
        
        // 아이템이 있으면 데미지 설정, 없으면 기본 데미지 1로 설정
        if (item != null && item.itemType == ItemType.Weapon)
        {
            attackDamage = item.damage;
        }
        else
        {
            attackDamage = 1f; // 기본 데미지
        }
    }
    
    // 공격 수행 함수
    private void Attack()
    {
        if (isAttacking) return; // 이미 공격 중이면 무시
        
        isAttacking = true;
        
        // 공격 애니메이션 재생
        if (animator != null)
        {
            animator.SetTrigger("1_Attack");
        }
        
        // 공격 데미지 적용 (딜레이 후)
        StartCoroutine(ApplyAttackDamage());
        
        // 공격 쿨다운 시작
        StartCoroutine(AttackCooldown());
    }
    
    // 공격 데미지 적용 코루틴
    private IEnumerator ApplyAttackDamage()
    {
        // 공격 애니메이션 시작 후 일정 시간 대기
        yield return new WaitForSeconds(attackDelay);
        
        // 공격 범위 내 적 감지
        Collider2D[] hitEnemies = Physics2D.OverlapCircleAll(attackPoint.position, attackRange, LayerMask.GetMask("Enemy"));
        
        // 감지된 모든 적에게 데미지 적용
        foreach (Collider2D enemy in hitEnemies)
        {
            EnemyHealth enemyHealth = enemy.GetComponent<EnemyHealth>();
            if (enemyHealth != null)
            {
                // 데미지 적용 (현재 위치 기준)
                enemyHealth.TakeDamage(attackDamage, attackPoint.position);
            }
        }
    }
}
```
</details>

<details>
        <summary>👩‍🦲NPC 상호작용 시스템    </summary>
   
```csharp
public class NpcInteraction : MonoBehaviour
{
    [Header("상호작용 설정")]
    [SerializeField] private float interactionRange = 2.0f;
    [SerializeField] private KeyCode interactionKey = KeyCode.F;
    
    [Header("UI 설정")]
    private GameObject interactionPrompt;    // NPC와 상호작용할 수 있을 때 표시되는 프롬프트 UI
    private GameObject npcInfoPanel;         // NPC 정보를 표시하는 패널
    
    // 참조 변수
    private Transform playerTransform;
    private Npc currentNpc;
    public bool isInteracting = false;
    
    // 가장 가까운 NPC 찾기
    private Npc FindNearestNpc()
    {
        Npc closestNpc = null;
        float closestDistance = interactionRange;
        
        Npc[] allNpcs = FindObjectsOfType<Npc>();
        foreach (Npc npc in allNpcs)
        {
            float distance = Vector3.Distance(playerTransform.position, npc.transform.position);
            if (distance < closestDistance)
            {
                closestDistance = distance;
                closestNpc = npc;
            }
        }
        
        return closestNpc;
    }
    
    // NPC와 상호작용 시작
    private void StartInteraction(Npc npc)
    {
        currentNpc = npc;
        isInteracting = true;
        
        // 플레이어 공격 비활성화
        Player player = playerTransform.GetComponent<Player>();
        if (player != null)
            player.isAttack = false;
        
        // NPC 정보 패널 표시
        if (npcInfoPanel)
        {
            npc.transform.GetChild(1).transform.Find("npcInfoPanel").gameObject.SetActive(true);
        }
        
        // 상호작용 프롬프트 숨기기
        if (interactionPrompt)
            npc.transform.GetChild(1).transform.Find("NPCPrompt").gameObject.SetActive(false);
        
        // NPC에게 상호작용 시작 알림
        npc.OnInteractionStart();
    }
}
```
</details>

<details>
        <summary>🏹화살 발사 NPC 시스템   </summary>
   
```csharp
public class ArrowShooter_Npc : MonoBehaviour
{
    public static bool isBowEquipped = false;
    public static int arrowDamage;
    public GameObject arrowPrefab; // 화살 프리팹
    public Transform shootPoint;  // 화살이 발사될 위치
    public float arcHeight = 2f; // 반원 또는 타원의 높이
    public float maxShootDistance = 10f; // 발사 가능 최대 X축 거리
    
    private Queue<GameObject> arrowPool = new Queue<GameObject>(); // 화살 오브젝트 풀
    private float lastShootTime = -999f;
    private Npc npc;
    
    void Update()
    {
        // NPC 자동 발사: 가장 가까운 몹이 일정 거리 이내면 쿨타임마다 자동 발사
        GameObject targetMob = FindNearestMob();
        if (targetMob == null) return;
        
        float distance = Mathf.Abs(shootPoint.position.x - targetMob.transform.position.x);
        if (distance > maxShootDistance) return;
        
        if (npc.bow.activeSelf == true)
        {
            isBowEquipped = true;
            arrowDamage = npc.attackDamage;
        }
        else
        {
            isBowEquipped = false;
        }
        
        if (Time.time - lastShootTime >= 1.0f) // 쿨타임 1초
        {
            if (isBowEquipped && ShootArrow())
            {
                lastShootTime = Time.time;
                GameManager.instance.PlaySFX("ArrowAttack");
            }
        }
    }
    
    // 화살 발사 함수
    public bool ShootArrow()
    {
        // 가장 가까운 몹 찾기
        GameObject targetMob = FindNearestMob();
        if (targetMob == null) return false;
        
        // 거리 체크
        float xDistanceToMob = Mathf.Abs(shootPoint.position.x - targetMob.transform.position.x);
        if (xDistanceToMob > maxShootDistance) return false;
        
        // 화살 가져오기
        GameObject arrow = GetPooledArrow();
        if (arrow == null) return false;
        
        // 화살 초기화 및 설정
        arrow.transform.position = shootPoint.position;
        arrow.SetActive(true);
        
        // 화살의 충돌 핸들러에 NPC별 공격력 세팅
        EffectCollisionHandler handler = arrow.GetComponent<EffectCollisionHandler>();
        if (handler != null)
        {
            handler.isNpcArrow = true; // NPC가 쏜 화살임을 표시
            handler.npcAttackDamage = npc.attackDamage; // 이 NPC의 공격력
        }
        
        // 화살 이동 코루틴 시작
        Vector3 startPosition = shootPoint.position + new Vector3(0, 2f, 0);
        Vector3 targetPosition = targetMob.transform.position + new Vector3(0, 2f, 0);
        StartCoroutine(MoveArrowInArc(arrow, startPosition, targetPosition));
        
        return true;
    }
}
```
</details>

<details>
        <summary>🤖NPC 인공지능 시스템   </summary>
   
```csharp
public class Npc : MonoBehaviour
{
    // NPC 상태
    public enum NpcState { Idle, Moving, Interacting, Escaping }
    private NpcState currentState = NpcState.Idle;

    // NPC 작업 유형
    public enum NpcTask
    {
        None,
        Woodcutting, // 나무 채집
        Mining,      // 광물 채집
        Combat,      // 전투
        BowCombat    // 활사용 전투
    }
    private NpcTask currentTask = NpcTask.None;
    
    [Header("이동 설정")]
    [SerializeField] private float moveSpeed = 1.0f;
    [SerializeField] private float idleTimeMin = 2.0f;
    [SerializeField] private float idleTimeMax = 5.0f;
    [SerializeField] private float moveTimeMin = 1.0f;
    [SerializeField] private float moveTimeMax = 3.0f;
    private float movementRange = 30.0f;
    
    // 다음 행동 결정
    private void DecideNextAction()
    {
        if (!randomMovementActive) return;
        
        // 랜덤 확률로 다음 행동 결정
        float randomValue = Random.value;
        
        if (isMoving)
        {
            // 이동 중이면 정지 상태로 전환
            isMoving = false;
            currentState = NpcState.Idle;
            rb.velocity = Vector2.zero;
            
            // 정지 시간 랜덤 설정
            idleTimer = Random.Range(idleTimeMin, idleTimeMax);
        }
        else
        {
            // 정지 중이면 이동 상태로 전환
            isMoving = true;
            currentState = NpcState.Moving;
            
            // 랜덤 방향 설정
            float randomAngle = Random.Range(0f, 360f);
            moveDirection = new Vector2(
                Mathf.Cos(randomAngle * Mathf.Deg2Rad),
                Mathf.Sin(randomAngle * Mathf.Deg2Rad)
            ).normalized;
            
            // 이동 시간 랜덤 설정
            moveTimer = Random.Range(moveTimeMin, moveTimeMax);
        }
    }
    
    // 정지 상태 처리
    private void HandleIdleState()
    {
        // 정지 타이머 감소
        idleTimer -= Time.deltaTime;
        
        // 타이머가 0 이하면 다음 행동 결정
        if (idleTimer <= 0f)
        {
            DecideNextAction();
        }
        
        // 애니메이션 업데이트
        if (animator != null)
        {
            animator.SetBool("1_Move", false);
        }
    }
    
    // 이동 상태 처리
    private void HandleMovingState()
    {
        // 이동 타이머 감소
        moveTimer -= Time.deltaTime;
        
        // 타이머가 0 이하면 다음 행동 결정
        if (moveTimer <= 0f)
        {
            DecideNextAction();
            return;
        }
        
        // 초기 위치에서 너무 멀어지면 방향 전환
        Vector3 distanceFromStart = transform.position - initialPosition;
        if (distanceFromStart.magnitude > movementRange)
        {
            // 초기 위치 방향으로 방향 전환
            moveDirection = -distanceFromStart.normalized;
        }
        
        // 이동 적용
        rb.velocity = moveDirection * moveSpeed;
        
        // 방향 업데이트
        UpdateDirection(moveDirection);
        
        // 애니메이션 업데이트
        if (animator != null)
        {
            animator.SetBool("1_Move", true);
        }
    }
    
    // 작업 처리
    private void HandleTask()
    {
        switch (currentTask)
        {
            case NpcTask.Woodcutting:
                HandleWoodcuttingTask();
                break;
                
            case NpcTask.Mining:
                HandleMiningTask();
                break;
                
            case NpcTask.Combat:
                HandleCombatTask();
                break;
                
            case NpcTask.BowCombat:
                HandleBowCombatTask();
                break;
        }
    }
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/공성-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/타워디펜스-f0ad4e?style=flat-square"/>
        <img src="https://img.shields.io/badge/생존-d9534f?style=flat-square"/>
        <img src="https://img.shields.io/badge/2D-5bc0de?style=flat-square"/>
      </div>
    </td>
  </tr>
  
  <tr>
    <td width="40%">
      <a href="https://youtu.be/NtjVl0uQS3w">
        <img src="https://www.notion.so/image/attachment%3Adad986e4-f841-4ac9-98ab-750e0d77e896%3Aimage.png?table=block&id=1dfddb27-d189-80f3-9126-d6206324c762&spaceId=6b98e78d-cc49-47f6-a0bf-9b1b0470f6ac&width=1420&userId=&cache=v2" width="100%" alt="룸 이스케이프"/>
      </a>
      <div align="center">
        <small><i>👆 이미지 클릭시 유튜브로 이동</i></small>
      </div>
    </td>
    <td width="60%">
      <h3>🚪 Room Escape - VR 콘텐츠 (2025.01.20 ~ 2025.02.08)</h3>
      <p>Unity XR과 Oculus Quest 2를 활용한 VR 탈출 게임입니다. 다양한 퍼즐과 상호작용 요소를 VR 환경에 맞게 구현했습니다.</p>
      <a href="https://github.com/younghoon99/Room-Escape" target="_blank">
  <img src="https://img.shields.io/badge/Room-Escape로_이동-757575?style=for-the-badge&logo=github&logoColor=white"/>
</a>
      
<details>
        <summary>♟레벨 관리 시스템   </summary>
   
```csharp
public class Level : MonoBehaviour
{
    [Header("기본값")]
    public List<GameObject> trapObject;    // 함정 오브젝트 리스트
    [SerializeField] private bool startYn = false;    // 시작여부
    public GameObject frameTrap;    // 프레임 함정이 없는 프레임
    
    [Header("현재 방")]
    [SerializeField] private int roomNumber;    // 방번호
    [SerializeField] private int randomNumber;    // 현재 함정 번호
    public List<GameObject> theTrapObject;    // 현재 함정 오브젝트 리스트
    
    // 오브젝트 상태 저장 구조체
    [System.Serializable]
    private struct ObjectState
    {
        public Vector3 position;      // 위치
        public Quaternion rotation;   // 회전값
        public bool isActive;         // 활성화 상태
    }
    
    // 함정 설정 메서드
    public void SetUpTrap()
    {
        // 레벨을 초기 상태로 리셋
        ResetLevelToInitialState();
        
        // 50% 확률로 함정 설치
        if (Random.Range(0, 2) == 0 && theTrapObject.Count > 0)
        {
            randomNumber = Random.Range(0, theTrapObject.Count);
            theTrapObject[randomNumber].SetActive(true);
            isTrap = true;
            if(frameTrap != null) frameTrap.SetActive(false);
        }
        else
        {
            isTrap = false;
            if(frameTrap != null) frameTrap.SetActive(true);
        }
    }
    
    // 트리거 충돌 처리
    private void OnTriggerEnter(Collider other)
    {
        if (other.gameObject.name == "starting" && startYn)
        {
            roomNumber++; // 방 번호 증가
            // 함정 처리 로직
            SetUpTrap();
            thisRoom.text = "Room : " + roomNumber;
            handUi.text = "Room : " + roomNumber;
        }
    }
}
```
</details>

<details>
        <summary>🎮게임 매니저   </summary>
   
```csharp
public class GameManager : MonoBehaviour
{
    public static GameManager instance;
    public Image image;
    public AudioClip lockerSound;  // 사물함 소리
    public AudioClip catSound;     // 고양이 소리
    public AudioSource doorSound;  // 문 여는 소리
    public AudioSource respawnSound;  // 리스폰 소리
    
    void Awake()
    {
        // 싱글톤 패턴 구현
        if (instance == null)
        {
            instance = this;
            DontDestroyOnLoad(gameObject);
        }
        else if (instance != this)
        {
            Destroy(gameObject);
        }
        
        // 오디오 소스 초기화
        if (doorSound == null) doorSound = gameObject.AddComponent<AudioSource>();
        if (respawnSound == null) respawnSound = gameObject.AddComponent<AudioSource>();
    }
    
    // 페이드 효과 구현
    public void FadeOut()
    {
        StartCoroutine(FadeCoroutine());
    }
    
    IEnumerator FadeCoroutine()
    {
        // 페이드 아웃
        float fadeCount = 0f;
        while (fadeCount < 1.0f)
        {
            fadeCount += 0.1f;
            yield return new WaitForSeconds(0.001f);
            image.color = new Color(0, 0, 0, fadeCount);
        }
        
        // 페이드 인
        yield return new WaitForSeconds(0.5f);
        fadeCount = 1f;
        while (fadeCount > 0.0f)
        {
            fadeCount -= 0.01f;
            yield return new WaitForSeconds(0.05f);
            image.color = new Color(0, 0, 0, fadeCount);
        }
    }
}
```
</details>

<details>
        <summary>🎲상호작용 시스템  </summary>
   
```csharp
public class OpenLocker : MonoBehaviour
{
    private bool isOpen = false;  // 문이 열려있는지 상태를 체크
    private Quaternion startRotation;  // 시작 회전값
    private Quaternion targetRotation;  // 목표 회전값
    public GameObject door;
    public float rotationSpeed = 1f;  // 회전 속도 조절 변수
    private AudioSource lockerAudio;  // 각 Locker의 개별 AudioSource
    
    void Start()
    {
        // 초기 회전값과 목표 회전값 설정
        startRotation = door.transform.rotation;
        targetRotation = Quaternion.Euler(0, startRotation.eulerAngles.y + -90f, 0);
        
        // 오디오 설정
        lockerAudio = gameObject.AddComponent<AudioSource>();
        lockerAudio.clip = GameManager.instance.lockerSound;
        lockerAudio.spatialBlend = 1f;  // 3D 사운드 설정
    }
    
    // 클릭 이벤트 처리
    public void OnClickOpen()
    {
        if (!isOpen) 
        { 
            PlayLockerSound(0f, 1f);
            StartCoroutine(OpenDoorSmooth());
            isOpen = !isOpen;
        }
        else if (isOpen)
        {
            PlayLockerSound(2f, 2.7f);
            StartCoroutine(CloseDoorSmooth());
            isOpen = !isOpen;
        }
    }
    
    // 부드러운 문 열기 애니메이션
    IEnumerator OpenDoorSmooth()
    {
        float elapsedTime = 0f;
        float duration = rotationSpeed;
        Quaternion currentRotation = door.transform.rotation;
        
        while (elapsedTime < duration)
        {
            door.transform.rotation = Quaternion.Lerp(currentRotation, targetRotation, elapsedTime / duration);
            elapsedTime += Time.deltaTime;
            yield return null;
        }
        
        door.transform.rotation = targetRotation;
    }
}
```
</details>
      <div>
        <img src="https://img.shields.io/badge/VR탈출게임-5cb85c?style=flat-square"/>
        <img src="https://img.shields.io/badge/Oculus-5bc0de?style=flat-square"/>
      </div>
    </td>
  </tr>
</table>


